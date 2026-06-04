# Sector Number Recovery in LevelDB

> A guide to recovering lost sector numbers from LevelDB after a miner node failure.
> Last updated: June 2026

---

## Table of Contents

1. [Understanding the Problem](#understanding-the-problem)
2. [What Are the Risks?](#what-are-the-risks)
3. [Prerequisites](#prerequisites)
4. [How Sector Data is Stored in LevelDB](#how-sector-data-is-stored-in-leveldb)
5. [Finding Missing Sector Numbers](#finding-missing-sector-numbers)
   - [Method 1: Using the Filecoin Blockchain Explorer](#method-1-using-the-filecoin-blockchain-explorer)
   - [Method 2: Using the Lotus API (JSON-RPC)](#method-2-using-the-lotus-api-json-rpc)
   - [Method 3: Using Lotus Shed](#method-3-using-lotus-shed)
   - [Method 4: Chain Traversal with Lotus CLI](#method-4-chain-traversal-with-lotus-cli)
6. [Recovering Sector Numbers in LevelDB](#recovering-sector-numbers-in-leveldb)
   - [Method A: Using Lotus Shed (Recommended)](#method-a-using-lotus-shed-recommended)
   - [Method B: Using Python plyvel (Manual)](#method-b-using-python-plyvel-manual)
   - [Method C: Using Go LevelDB Tool](#method-c-using-go-leveldb-tool)
7. [Verification](#verification)
8. [Preventing Future Data Loss](#preventing-future-data-loss)
9. [Troubleshooting](#troubleshooting)

---

## Understanding the Problem

### Scenario

```
Time → 
│
├─ T1: Backup taken (sectors 1-100 in LevelDB backup)
├─ T2: Normal operation (sectors 101-150 created/sealed)
├─ T3: ⚠️ Miner node failure (crash/data corruption)
├─ T4: Restore from backup (only sectors 1-100)
└─ T5: ❌ Sectors 101-150 are "lost" — not in the restored DB
```

When a Lotus miner node fails and you restore from a backup:
1. The backup contains the sector tracking database at the time of backup
2. Any sectors **created after the backup** are not in the restored database
3. The miner is unaware of these sectors — they appear as "missing"
4. The network still knows about these sectors (they're on-chain)
5. If not recovered, the sectors become **faulty** and incur daily penalties

### How Sectors Get Lost

| Cause | Description |
|-------|-------------|
| **Disk failure** | LevelDB data on corrupted storage |
| **Accidental deletion** | Operator removes or overwrites the datastore directory |
| **Node migration** | Improper migration between machines |
| **Corrupt LevelDB** | Unexpected shutdown corrupts the LSM tree |
| **Clone/Restore error** | Restoring from an outdated snapshot |

---

## What Are the Risks?

### Financial Impact

If lost sector numbers are not recovered:

| Consequence | Impact |
|-------------|:------:|
| **Sector Fault Fee** | ~2.14 days of expected block reward per sector per day |
| **Termination Penalty** | Sector's expected reward × 20 + gas costs |
| **Power Loss** | Lost sectors contribute 0 to storage power |
| **Deal Penalties** | If deals were in the lost sectors, provider reputation suffers |

### Calculation Example

```
For a miner with 10 TiB (320 × 32 GiB sectors):

Lost sectors: 50 sectors (1.5 TiB)
Daily fault fee per sector: ~0.005 FIL
Total daily penalty: 50 × 0.005 = 0.25 FIL
Monthly: ~7.5 FIL
Before recovery: ❌ Ongoing penalties
After recovery: ✅ No penalties, full power restored
```

### Chain State vs Local State

It's important to understand the distinction:

- **Chain State (Network)**: The Filecoin blockchain has **all** your sector information — sector numbers, commitment proofs, deals. This is immutable.
- **Local State (LevelDB)**: Your miner tracks sector metadata locally for operations (WindowPoST scheduling, sealing status, deal tracking).

When you recover lost sector numbers, you're **repairing local state** to match chain state. The network already knows your sectors exist — you just need to make your miner aware of them again.

---

## Prerequisites

### Tools You'll Need

| Tool | Purpose | Installation |
|------|---------|-------------|
| **lotus-shed** | Inspector/repair tool for Lotus DB | Built with Lotus (`make lotus-shed`) |
| **lotus-miner** | Your running miner CLI | Standard Lotus installation |
| **plyvel** | Python LevelDB library | `pip3 install plyvel` |
| **ldb** | LevelDB CLI tool | `go install github.com/syndtr/goleveldb/leveldb/cmd/ldb@latest` |
| **jq** | JSON processor for API responses | `sudo apt install jq` |
| **curl** | API calls to Lotus node | `sudo apt install curl` |

### Safety First

> ⚠️ **IMPORTANT**: Before making any changes to LevelDB:
> 1. **Stop your miner**: `lotus-miner stop`
> 2. **Back up the current database**: `cp -a ~/.lotusminer ~/.lotusminer.backup.$(date +%Y%m%d)`
> 3. **Back up the chain data**: `cp -a ~/.lotus ~/.lotus.backup.$(date +%Y%m%d)`
> 4. **Test on a non-production node first if possible**

### Locate Your LevelDB Databases

Lotus stores databases in different locations depending on your configuration:

```bash
# Default miner data directory
ls ~/.lotusminer/

# LevelDB databases are typically under:
# ~/.lotusminer/kvlog/          - KV log entry database
# ~/.lotusminer/datastore/      - Main datastore (could be Badger or LevelDB)
# ~/.lotusminer/sectorstore.json - Sector storage configuration

# Check which datastore type is in use
ls ~/.lotusminer/datastore/
```

The exact path varies by Lotus version and configuration. The key database files are:
- **Chain datastore**: Usually Badger or LevelDB under `~/.lotus/datastore/`
- **Miner datastore**: LevelDB under `~/.lotusminer/datastore/`
- **Sector metadata**: May be in a separate LevelDB or embedded in the main datastore

---

## How Sector Data is Stored in LevelDB

### LevelDB Structure

Lotus uses [LevelDB](https://github.com/google/leveldb) (an LSM-tree key-value store) for local metadata. Sector information is stored with specific key prefixes:

```
Key format examples (hex-encoded keys):
├── /sector/info/<sectorNumber>        → Sector metadata (seal status, deals, etc.)
├── /sector/precommit/<sectorNumber>  → Pre-commit information
├── /sector/commit/<sectorNumber>     → Commit proof information
├── /deals/<dealID>                   → Deal metadata
└── /miner/info                       → Miner configuration
```

**Note**: The exact key schema depends on the Lotus version. The most important keys to recover are the `sector/info` entries that tell the miner which sectors exist.

### What Happens During Recovery

When you restore from a backup:

```text
Backup LevelDB (before failure):
  /sector/info/1  → {state: "Proving", deal: 1001}
  /sector/info/2  → {state: "Proving", deal: 1002}
  ...
  /sector/info/100 → {state: "Proving", deal: 1100}
  
Live LevelDB after failure & restore:
  /sector/info/1  → {state: "Proving", deal: 1001}   ✅ Recovered
  /sector/info/2  → {state: "Proving", deal: 1002}   ✅ Recovered
  ...
  /sector/info/100 → {state: "Proving", deal: 1100}  ✅ Recovered

Missing (created after backup, not in LevelDB):
  /sector/info/101  ❌
  /sector/info/102  ❌
  ...
  /sector/info/150  ❌
```

The recovery goal is to re-insert the missing sector entries.

---

## Finding Missing Sector Numbers

Before you can recover sectors, you need to know **which sectors are missing**. There are several methods:

### Method 1: Using the Filecoin Blockchain Explorer

This is the easiest method, suitable for small numbers of sectors.

#### Step 1: Find your miner's address

```bash
lotus-miner info | grep "Miner:"
# Output: Miner: f0123456
```

#### Step 2: Use a blockchain explorer

Visit one of these explorers and search for your miner ID:

| Explorer | URL | Features |
|----------|-----|----------|
| **FilScan** | https://filscan.io | Full sector list, deal info, power stats |
| **FilFox** | https://filfox.info | Sector explorer with pagination |
| **Starboard** | https://filrep.io | Storage provider dashboard |
| **FilInfo** | https://filinfo.info | Lightweight sector viewer |

#### Step 3: Export the sector list

On **FilScan** (example):
1. Search for your miner ID (e.g., `f0123456`)
2. Go to the **Sectors** tab
3. Note the highest and lowest sector numbers
4. Compare with your local sector list

#### Step 4: Compare with local state

```bash
# List local sectors from the backup
lotus-miner sectors list 2>/dev/null | awk '{print $1}' | sort -n > /tmp/local-sectors.txt

# Compare with explorer data
# Manually note sectors present in explorer but missing locally
```

---

### Method 2: Using the Lotus API (JSON-RPC)

This method is programmatic and suitable for automation.

#### Step 1: Enable the Lotus API

Ensure your Lotus daemon is running with the API enabled:

```bash
# Check if API is listening
lotus net listen

# If not, start with API enabled
lotus daemon --api 1234
```

#### Step 2: Query miner sectors via RPC

```bash
#!/bin/bash
# find-missing-sectors.sh
# Uses Lotus RPC to list all on-chain sectors for a miner

MINER_ID="f0123456"  # Replace with your miner ID

# Get the current chain head
HEAD=$(lotus chain head | head -1)

# Query the miner's sector allocation
# Method: Filecoin.StateMinerSectors
lotus state miner-sectors "$MINER_ID" 2>/dev/null | \
  jq -r '.[].ID.SectorNumber' | sort -n > /tmp/chain-sectors.txt

echo "On-chain sectors: $(wc -l < /tmp/chain-sectors.txt)"
echo "First 10:"
head -10 /tmp/chain-sectors.txt
```

#### Step 3: Compare chain vs local

```bash
# Get local sectors from the backup-restored miner
lotus-miner sectors list 2>/dev/null | \
  awk '{print $1}' | sort -n > /tmp/local-sectors.txt

# Find the difference (sectors on chain but not local)
comm -23 /tmp/chain-sectors.txt /tmp/local-sectors.txt > /tmp/missing-sectors.txt

echo "Missing sectors: $(wc -l < /tmp/missing-sectors.txt)"
cat /tmp/missing-sectors.txt
```

#### Step 4: RPC Script for Detailed Sector Info

For more detailed information about each missing sector:

```python
#!/usr/bin/env python3
"""get_sector_info.py - Query chain state for missing sectors"""

import json
import subprocess
import sys

MINER_ID = "f0123456"  # Replace with your miner ID
MINER_ID_NUM = int(MINER_ID.replace("f0", "").replace("t0", ""))

def lotus_call(method, params):
    """Call Lotus JSON-RPC API"""
    payload = {
        "jsonrpc": "2.0",
        "method": f"Filecoin.{method}",
        "params": params,
        "id": 1
    }
    result = subprocess.run(
        ["lotus", "chain", "head"],
        capture_output=True, text=True, timeout=10
    )
    return result.stdout.strip()

def get_sector_info(miner_id, sector_num):
    """Get sector info from chain state"""
    result = subprocess.run(
        ["lotus", "state", "sector", str(sector_num), miner_id],
        capture_output=True, text=True, timeout=30
    )
    if result.returncode == 0 and result.stdout.strip():
        return result.stdout.strip()
    return None

# Read missing sector numbers
if len(sys.argv) > 1:
    missing_file = sys.argv[1]
else:
    print("Usage: python3 get_sector_info.py /tmp/missing-sectors.txt")
    sys.exit(1)

with open(missing_file) as f:
    sectors = [int(line.strip()) for line in f if line.strip()]

print(f"Checking {len(sectors)} missing sectors...")
for sector_num in sectors:
    info = get_sector_info(MINER_ID, sector_num)
    if info:
        print(f"Sector {sector_num}: EXISTS on chain ✅")
        # Print first 200 chars of info
        print(f"  {info[:200]}")
    else:
        print(f"Sector {sector_num}: ERROR querying chain state ❌")
```

---

### Method 3: Using Lotus Shed

`lotus-shed` is a tool built with Lotus for database inspection and repair.

#### Step 1: Build lotus-shed

```bash
cd $GOPATH/src/github.com/filecoin-project/lotus
make lotus-shed
sudo cp lotus-shed /usr/local/bin/
```

#### Step 2: Examine the LevelDB database

```bash
# List all keys in the datastore (miner)
lotus-shed datastore list \
  --repo ~/.lotusminer 2>&1 | head -50

# Search for sector-related keys
lotus-shed datastore list \
  --repo ~/.lotusminer 2>&1 | grep -i "sector" | head -20

# Count sector info entries
lotus-shed datastore list \
  --repo ~/.lotusminer 2>&1 | grep "/sector/info" | wc -l
```

#### Step 3: Dump sector info from chain

```bash
# Use lotus-shed to compare chain vs local sectors
lotus-shed sectors check \
  --miner f0123456 2>&1

# This command should highlight:
# - Sectors present on chain but missing in local DB
# - Sectors present locally but not on chain (orphans)
# - Sector state mismatches
```

---

### Method 4: Chain Traversal with Lotus CLI

#### Step 1: Query sector set from chain

```bash
# Method: StateMinerSectors returns all sector IDs for a miner
lotus state miner-sectors f0123456 2>/dev/null | \
  python3 -c "
import json, sys
data = json.load(sys.stdin)
if isinstance(data, list):
    sectors = [s['ID']['SectorNumber'] for s in data]
elif isinstance(data, dict) and 'Sectors' in data:
    sectors = [s['ID']['SectorNumber'] for s in data['Sectors']]
else:
    sectors = []
sectors.sort()
print(f'Total sectors on chain: {len(sectors)}')
print(f'Range: {sectors[0]} - {sectors[-1]}')
with open('/tmp/chain-sectors.txt', 'w') as f:
    for s in sectors:
        f.write(f'{s}\\n')
print('Saved to /tmp/chain-sectors.txt')
"
```

#### Step 2: Compare with local sectors

```bash
# Get local sectors list
lotus-miner sectors list 2>/dev/null | awk '{print $1}' | sort -n > /tmp/local-sectors.txt

# Find missing
comm -23 /tmp/chain-sectors.txt /tmp/local-sectors.txt > /tmp/missing-sectors.txt

echo "=== Missing Sectors ==="
cat /tmp/missing-sectors.txt
echo "Total missing: $(wc -l < /tmp/missing-sectors.txt)"
```

---

## Recovering Sector Numbers in LevelDB

Once you have identified the missing sector numbers, you need to inject them back into the LevelDB database.

### Method A: Using Lotus Shed (Recommended)

This is the safest and most straightforward method.

#### Step 1: Stop the miner

```bash
lotus-miner stop
sleep 5

# Verify stopped
lotus-miner info 2>&1 | grep -q "could not get API" && echo "Miner stopped ✅" || echo "Miner still running ❌"
```

#### Step 2: Back up the current database

```bash
cp -a ~/.lotusminer ~/.lotusminer.backup.$(date +%Y%m%d)
echo "Backup created at ~/.lotusminer.backup.$(date +%Y%m%d)"
```

#### Step 3: Insert missing sectors using lotus-shed

```bash
# For each missing sector, insert a minimal entry
# This tells the miner that the sector exists and should be tracked

cat /tmp/missing-sectors.txt | while read sector; do
    echo "Recovering sector $sector..."
    
    # Insert sector info entry
    lotus-shed datastore put \
      --repo ~/.lotusminer \
      --key "/sector/info/$sector" \
      --value '{"SectorNumber":'"$sector"',"SealProof":8,"State":7}' 2>&1
    
    # Insert pre-commit entry if applicable
    lotus-shed datastore put \
      --repo ~/.lotusminer \
      --key "/sector/precommit/$sector" \
      --value '{"SectorNumber":'"$sector"',"State":2}' 2>&1
    
    echo "  ✅ Sector $sector inserted"
done
```

> **⚠️ Important**: The exact key format and value schema depend on your Lotus version. Check the lotus source code or use `lotus-shed datastore get` on an existing healthy entry to see the format:
> ```bash
> lotus-shed datastore get --repo ~/.lotusminer --key "/sector/info/1"
> ```

#### Step 4: Verify the insertion

```bash
# Check that the keys were inserted
for sector in $(cat /tmp/missing-sectors.txt); do
    result=$(lotus-shed datastore get --repo ~/.lotusminer --key "/sector/info/$sector" 2>&1)
    if echo "$result" | grep -q "Error\|not found"; then
        echo "Sector $sector: STILL MISSING ❌"
    else
        echo "Sector $sector: RECOVERED ✅"
    fi
done
```

---

### Method B: Using Python plyvel (Manual)

If `lotus-shed` is not available or you need more control, use Python.

#### Step 1: Install plyvel

```bash
# plyvel requires LevelDB native library
sudo apt install -y libleveldb-dev
pip3 install plyvel
```

#### Step 2: Recovery script

```python
#!/usr/bin/env python3
"""
leveldb-sector-recovery.py
Recover missing sector numbers in Lotus LevelDB datastore.

Usage:
  python3 leveldb-sector-recovery.py /tmp/missing-sectors.txt

WARNING: Stop your lotus-miner before running this script!
"""

import json
import os
import sys
import shutil
import plyvel
from datetime import datetime

# Configure paths
MINER_DB_PATH = os.path.expanduser("~/.lotusminer/datastore")
BACKUP_PATH = f"{MINER_DB_PATH}.backup.{datetime.now().strftime('%Y%m%d_%H%M%S')}"

def create_backup():
    """Create a backup of the current database"""
    if os.path.exists(MINER_DB_PATH):
        print(f"Creating backup: {BACKUP_PATH}")
        shutil.copytree(MINER_DB_PATH, BACKUP_PATH)
        print("Backup created ✅")
    else:
        print(f"Warning: {MINER_DB_PATH} not found")
        print("Trying alternative paths...")
        # Try common locations
        alt_paths = [
            os.path.expanduser("~/.lotusminer"),
            os.path.expanduser("~/.lotusminer/kvlog"),
        ]
        for p in alt_paths:
            if os.path.exists(p):
                print(f"Found: {p}")
                return p
        return None
    return MINER_DB_PATH

def open_db(db_path):
    """Open LevelDB database"""
    try:
        db = plyvel.DB(db_path, create_if_missing=False)
        print(f"Opened database: {db_path}")
        return db
    except Exception as e:
        print(f"Error opening database: {e}")
        return None

def get_chain_sectors(miner_id):
    """Query chain for all sector numbers"""
    import subprocess
    try:
        result = subprocess.run(
            ["lotus", "state", "miner-sectors", miner_id],
            capture_output=True, text=True, timeout=60
        )
        if result.returncode != 0 or not result.stdout.strip():
            print(f"Warning: Could not query chain: {result.stderr[:200]}")
            return set()
        
        data = json.loads(result.stdout)
        sectors = set()
        if isinstance(data, list):
            for s in data:
                sectors.add(s['ID']['SectorNumber'])
        elif isinstance(data, dict):
            for s in data.get('Sectors', data.get('sectors', [])):
                sectors.add(s['ID']['SectorNumber'])
        return sectors
    except Exception as e:
        print(f"Error querying chain: {e}")
        return set()

def get_local_sectors(db):
    """Get sector numbers from local LevelDB"""
    sectors = set()
    try:
        for key_bytes, value_bytes in db:
            key = key_bytes.decode('utf-8', errors='replace')
            if '/sector/info/' in key:
                try:
                    sector_num = int(key.split('/')[-1])
                    sectors.add(sector_num)
                except ValueError:
                    pass
        return sectors
    except Exception as e:
        print(f"Error scanning local DB: {e}")
        return sectors

def find_missing(db=None, miner_id=None):
    """Find sectors that are on chain but missing in local DB"""
    chain = get_chain_sectors(miner_id) if miner_id else set()
    
    if db:
        local = get_local_sectors(db)
        missing = chain - local
    else:
        missing = chain
    
    return sorted(missing)

def insert_sector_entry(db, sector_num):
    """Insert a minimal sector info entry"""
    key = f"/sector/info/{sector_num}".encode('utf-8')
    
    # Create a minimal sector info value
    # Adjust this based on your Lotus version
    value = {
        "SectorNumber": sector_num,
        "SealProof": 8,  # 32 GiB sector
        "State": 7,      # 7 = Proving state (common for active sectors)
        "DealIDs": [],
        "CreationTime": int(datetime.now().timestamp()),
    }
    
    try:
        db.put(key, json.dumps(value).encode('utf-8'))
        return True
    except Exception as e:
        print(f"  Error inserting sector {sector_num}: {e}")
        return False

def main():
    if len(sys.argv) > 1:
        missing_file = sys.argv[1]
        with open(missing_file) as f:
            missing_sectors = [int(line.strip()) for line in f if line.strip()]
    else:
        print("No missing sectors file provided.")
        print("Will try to auto-detect by comparing with chain state.")
        
        # Auto-detect
        db_path = create_backup()
        if not db_path:
            print("Could not find database. Specify manually.")
            sys.exit(1)
        
        db = open_db(db_path)
        if not db:
            sys.exit(1)
        
        miner_id = input("Enter your miner ID (e.g., f0123456): ").strip()
        missing_sectors = find_missing(db, miner_id)
        
        if not missing_sectors:
            print("No missing sectors found!")
            db.close()
            sys.exit(0)
    
    print(f"\nFound {len(missing_sectors)} missing sectors:")
    print(f"  {missing_sectors[:10]}{'...' if len(missing_sectors) > 10 else ''}")
    
    # Confirm
    confirm = input(f"\nInsert {len(missing_sectors)} sector entries? (yes/no): ")
    if confirm.lower() != 'yes':
        print("Aborted.")
        return
    
    # Insert
    db_path = create_backup()
    db = open_db(db_path)
    if not db:
        sys.exit(1)
    
    success = 0
    for sector in missing_sectors:
        if insert_sector_entry(db, sector):
            success += 1
        else:
            print(f"  ❌ Sector {sector} failed")
    
    db.close()
    
    print(f"\n✅ Recovery complete: {success}/{len(missing_sectors)} sectors inserted")
    print(f"⚠️  Backup saved at: {BACKUP_PATH}")
    print("\nNext steps:")
    print("1. Start your lotus-miner: lotus-miner run &")
    print("2. Verify recovery: lotus-miner sectors list | wc -l")
    print("3. Check for faults: lotus-miner proving faults")

if __name__ == "__main__":
    main()
```

#### Step 3: Run the recovery script

```bash
# Step 1: Stop the miner
lotus-miner stop

# Step 2: Run recovery (auto-detect mode)
python3 leveldb-sector-recovery.py

# OR: Run with pre-computed missing sector list
python3 leveldb-sector-recovery.py /tmp/missing-sectors.txt

# Step 3: Start the miner
lotus-miner run &
```

---

### Method C: Using Go LevelDB Tool

For advanced users comfortable with Go:

#### Step 1: Install the LevelDB tool

```bash
go install github.com/syndtr/goleveldb/leveldb/cmd/ldb@latest
```

#### Step 2: Inspect and modify

```bash
# List all keys in the database
ldb -db ~/.lotusminer/datastore scan

# Search for sector keys
ldb -db ~/.lotusminer/datastore scan | grep "sector" | head -20

# Get a specific sector entry (to understand the format)
ldb -db ~/.lotusminer/datastore get "/sector/info/1"

# Insert a missing sector (using hex-encoded value)
ldb -db ~/.lotusminer/datastore put \
  "/sector/info/101" \
  '{"SectorNumber":101,"SealProof":8,"State":7}'
```

---

## Verification

After recovery, verify everything is working correctly.

### Step 1: Start the miner

```bash
lotus-miner run &
sleep 30
```

### Step 2: Check sector list

```bash
# Count total sectors
lotus-miner sectors list | wc -l

# Should roughly match the number on chain
lotus state miner-sectors f0123456 2>/dev/null | \
  python3 -c "import json,sys;d=json.load(sys.stdin);print(len(d if isinstance(d,list) else d.get('Sectors',[])))"

# The numbers should be close (may differ if some sectors were terminated)
```

### Step 3: Check for faults

```bash
lotus-miner proving faults

# Should show no unexpected faults from the recovered sectors
```

### Step 4: Monitor WindowPoST

```bash
lotus-miner proving info
# Check that deadlines and partitions look correct

# Monitor for the next proving period
lotus-miner proving deadlines
```

### Step 5: Verify database integrity

```bash
# Check for database corruption
lotus-shed datastore check --repo ~/.lotusminer 2>&1 | grep -i "error\|corrupt"
# No errors expected

# Verify sector state consistency
lotus-miner sectors status --show-all 1 2>/dev/null | head -10
# Should show correct state for recovered sectors
```

---

## Preventing Future Data Loss

### 1. Regular Database Backups

```bash
#!/bin/bash
# backup-lotus-db.sh - Run nightly via cron

BACKUP_DIR="/mnt/backups/lotus"
DATE=$(date +%Y%m%d_%H%M%S)
MINER_REPO="$HOME/.lotusminer"

# Create backup with rotation (keep last 7 days)
find "$BACKUP_DIR" -name "lotusminer-*.tar.gz" -mtime +7 -delete

# Stop miner, backup, restart
lotus-miner stop
sleep 10

tar -czf "$BACKUP_DIR/lotusminer-$DATE.tar.gz" -C "$(dirname $MINER_REPO)" "$(basename $MINER_REPO)"

lotus-miner run &

echo "Backup created: lotusminer-$DATE.tar.gz"
echo "Backup size: $(du -h "$BACKUP_DIR/lotusminer-$DATE.tar.gz" | cut -f1)"
```

Add to crontab:
```bash
# Run daily at 3 AM
0 3 * * * /home/lotus/scripts/backup-lotus-db.sh >> /var/log/lotus-backup.log 2>&1
```

### 2. Enable Automatic Recovery Monitoring

```bash
#!/bin/bash
# monitor-sectors.sh - Check for sector mismatches

MINER_ID="f0123456"

# Get chain sector count
CHAIN_COUNT=$(lotus state miner-sectors "$MINER_ID" 2>/dev/null | \
  python3 -c "import json,sys;d=json.load(sys.stdin);print(len(d))" 2>/dev/null)

# Get local sector count
LOCAL_COUNT=$(lotus-miner sectors list 2>/dev/null | wc -l)

# Alert if mismatch is significant (>1%)
DIFF=$((CHAIN_COUNT - LOCAL_COUNT))
if [ "$DIFF" -gt "$((CHAIN_COUNT / 100))" ]; then
    echo "⚠️  Sector mismatch detected: $CHAIN_COUNT on chain vs $LOCAL_COUNT local"
    echo "Missing $DIFF sectors — run recovery procedure!"
fi
```

### 3. Best Practices

| Practice | Recommendation |
|----------|---------------|
| **Backup frequency** | Daily backups for production miners |
| **Backup retention** | Keep at least 7 days of backups |
| **Off-site backup** | Replicate to separate storage or cloud |
| **Test recovery** | Practice the recovery process on testnet first |
| **Monitoring** | Set up alerts for sector count mismatches |
| **Version control** | Note which Lotus version created each backup |

---

## Troubleshooting

### ❌ "Database in use" error

```
Error: IO error: lock ~/.lotusminer/datastore/LOCK: Resource temporarily unavailable
```

**Cause**: The miner or lotus daemon is still running.
**Fix**:
```bash
lotus-miner stop
lotus daemon stop
sleep 10
# Verify no processes remain
pgrep -a lotus
```

### ❌ Missing sectors not found on chain either

**Symptom**: Missing sectors list is empty after comparing with chain.
**Cause**: The sectors may have been terminated or expired on-chain.
**Fix**: 
```bash
# Check terminated sectors
lotus state miner-sectors f012456 --show-removed 2>/dev/null

# These sectors cannot be recovered — they are gone permanently
# File a pledge for new sectors instead
```

### ❌ plyvel import error

```
ImportError: libsnappy.so.1: cannot open shared object file
```

**Fix**:
```bash
sudo apt install -y libleveldb-dev libsnappy-dev
pip3 install --force-reinstall plyvel
```

### ❌ Lotus-shed command not found

**Fix**:
```bash
cd ~/lotus
make lotus-shed
sudo cp lotus-shed /usr/local/bin/
```

### ❌ Inserted sectors don't show up

**Symptom**: After inserting sector entries and restarting the miner, sectors are still not visible.
**Fix**:
1. Check the key format matches what Lotus expects
2. Try a different key prefix (the format changes between Lotus versions)
3. Use `lotus-shed datastore list` to examine an existing sector's key format
4. Check Lotus logs: `journalctl -u lotus-miner -n 200`

### ❌ Miner panics after recovery

**Symptom**: Lotus miner crashes immediately after starting with recovered data.
**Fix**:
1. Restore from backup: `cp -a ~/.lotusminer.backup.DATE ~/.lotusminer`
2. Try a different recovery method (e.g., use plyvel instead of lotus-shed)
3. The sector state value may be wrong — check the correct enum value for "Proving" in your Lotus version

---

## Quick Reference Card

```text
┌─────────────────────────────────────────────────────────────────┐
│         LEVELDB SECTOR RECOVERY QUICK REFERENCE                  │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│  1. STOP MINER                                                   │
│     lotus-miner stop                                             │
│                                                                  │
│  2. BACKUP                                                       │
│     cp -a ~/.lotusminer ~/.lotusminer.BACKUP                    │
│                                                                  │
│  3. FIND MISSING SECTORS                                         │
│     lotus state miner-sectors f0123456 > /tmp/chain-sectors.txt │
│     lotus-miner sectors list > /tmp/local-sectors.txt            │
│     comm -23 /tmp/chain-sectors.txt /tmp/local-sectors.txt       │
│                                                                  │
│  4. INSERT (using lotus-shed)                                    │
│     for s in $(cat /tmp/missing-sectors.txt); do                 │
│       lotus-shed datastore put                                   │
│         --key "/sector/info/$s"                                  │
│         --repo ~/.lotusminer                                     │
│         --value '{"SectorNumber":'$s',"SealProof":8,"State":7}' │
│     done                                                         │
│                                                                  │
│  5. VERIFY                                                       │
│     lotus-miner run &                                            │
│     lotus-miner sectors list | wc -l                             │
│     lotus-miner proving faults                                   │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

*This guide is part of the Filecoin Storage Provider Bounty Program. For corrections or updates, please open a PR or issue.*

*Part of the [Storage Provider Bounty Program](https://github.com/filecoin-project/community/blob/main/storage-provider-bounty-program/README.md)*
