# Multi-Sign Address Guide for Filecoin Storage Providers

> A comprehensive guide to using multi-signature addresses with Lotus miners for enhanced security.
> Last updated: June 2026

---

## Table of Contents

1. [Overview](#overview)
2. [What is a Multi-Sign Address?](#what-is-a-multi-sign-address)
3. [Why Use Multi-Sign for Your Miner Owner Address?](#why-use-multi-sign-for-your-miner-owner-address)
4. [Prerequisites](#prerequisites)
5. [Creating a Multi-Sign Address](#creating-a-multi-sign-address)
6. [Changing Owner Address Types](#changing-owner-address-types)
   - [Ordinary Address → Multi-Sign Address](#1-ordinary-address--multi-sign-address)
   - [Multi-Sign Address → Different Multi-Sign Address](#2-multi-sign-address--different-multi-sign-address)
   - [Multi-Sign Address → Single-Sign (Ordinary) Address](#3-multi-sign-address--single-sign-ordinary-address)
7. [Common Operations with Multi-Sign Owner](#common-operations-with-multi-sign-owner)
   - [Withdrawing Balance](#1-withdrawing-balance)
   - [Modifying Control Addresses](#2-modifying-control-addresses)
   - [Modifying Worker Address](#3-modifying-worker-address)
8. [Workflow Summary](#workflow-summary)
9. [Security Considerations](#security-considerations)
10. [Troubleshooting](#troubleshooting)

---

## Overview

A **multi-signature (multi-sign) address** requires approval from multiple parties before a transaction can be executed. This guide explains how to:

- Set up a multi-sign address for your miner owner address
- Transition between ordinary, multi-sign, and single-sign addresses
- Perform common miner operations (withdraw, change control addresses, change worker) when the owner is a multi-sign address
- Understand the security implications and best practices

---

## What is a Multi-Sign Address?

A multi-sign address is a smart contract on the Filecoin network that requires **M-of-N signatures** to authorize a transaction (where M = required signatures, N = total signers).

```
Example: 2-of-3 Multi-Sign Address

Signers:
  ┌────────┐  ┌────────┐  ┌────────┐
  │ Alice  │  │  Bob   │  │ Carol  │
  └────────┘  └────────┘  └────────┘
       │            │           │
       └────────────┼───────────┘
                    ▼
        ┌──────────────────────┐
        │   Multi-Sign Address  │
        │   (2 of 3 required)  │
        └──────────────────────┘
                    │
                    ▼
        ┌──────────────────────┐
        │   Miner Owner       │
        └──────────────────────┘

Transaction flow:
  1. Alice proposes → create transfer
  2. Bob approves → 2nd signature
  3. Transaction executes (threshold met)
```

### Key Properties

| Property | Description |
|----------|-------------|
| **Threshold** | Number of approvals required (e.g., 2) |
| **Signers** | List of addresses authorized to approve (<0x1234, 0x5678, 0x9ABC>) |
| **Transfer ID** | Unique ID for each pending proposal |
| **Approval** | A signer confirms the pending proposal |

---

## Why Use Multi-Sign for Your Miner Owner Address?

The **owner address** holds absolute power over a miner — it can:

- Change the worker address
- Withdraw funds
- Transfer ownership
- Change control addresses
- Terminate sectors

Using a multi-sign address as the owner:

✅ **Eliminates single point of failure** — No single compromised key can take over your miner  
✅ **Requires collusion for attacks** — An attacker needs M-of-N keys  
✅ **Enables team governance** — Distributed responsibility across team members  
✅ **Audit trail** — Every operation requires explicit approvals  
✅ **Recovery** — If one key is lost, the remaining signers can still operate (if threshold < N)

---

## Prerequisites

Before starting, ensure you have:

1. **Lotus installed** (v1.13.2 or later recommended)
   ```bash
   lotus version
   ```

2. **Running Lotus daemon** (synced to the network)
   ```bash
   lotus sync status
   ```

3. **Existing miner with an owner address**
   ```bash
   lotus-miner info
   ```

4. **Multiple wallet addresses** for setting up signers
   ```bash
   # Create new wallet addresses as needed
   lotus wallet new bls
   lotus wallet new secp256k1
   ```

5. **Sufficient FIL balance** — Multi-sign operations require gas fees for each proposal and approval

---

## Creating a Multi-Sign Address

Use `lotus msig create` to set up a multi-sign address:

```bash
# Create a 2-of-3 multi-sign address
lotus msig create \
  --required=2 \
  --duration=0 \
  <address1> <address2> <address3>
```

**Parameters:**

| Parameter | Description | Example |
|-----------|-------------|---------|
| `--required` | Number of signers needed to approve | `2` |
| `--duration` | Lock duration in epochs (0 = no lock) | `0` |
| `<addresses>` | Signer wallet addresses (space-separated) | `t1abc... t1def... t1ghi...` |

**Sample output:**
```
Created new multisig:  t2xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx  (2/3)
```

Save this multi-sign address — you'll use it as your new owner address.

> **💡 Tip**: For Filecoin storage providers, a **2-of-3** configuration is recommended:
> - Your primary workstation key (signer 1)
> - Your backup/team member key (signer 2)
> - A cold storage/hardware wallet key (signer 3 — use only for emergencies)

---

## Changing Owner Address Types

### 1. Ordinary Address → Multi-Sign Address

This is the most common transition — upgrading your single-signer owner to a multi-sign owner.

#### Step 1: Create and fund the multi-sign address

```bash
# Create 2-of-3 multi-sign address
lotus msig create --required=2 <signer1> <signer2> <signer3>
# → t2multisigAddress
```

#### Step 2: Propose the owner change

From any signer's address:

```bash
lotus-miner actor-msig set-owner \
  --really-do-it=true \
  --from=<proposerAddress> \
  <multisigAddress> \
  <multisigAddress>
```

| Parameter | Description |
|-----------|-------------|
| `--really-do-it=true` | Confirm the operation |
| `--from=<proposerAddress>` | The signer initiating the proposal (must be a signer of the *new* multi-sign address) |
| First `<multisigAddress>` | The **new owner** (your multi-sign address) |
| Second `<multisigAddress>` | The new **beneficiary** address |

> **⚠️ Note**: Both owner and beneficiary can be set to the same multi-sign address. The multi-sign address uses itself as both parameters because it's acting as its own authority.

#### Step 3: Approve the proposal

Other signers approve the pending transfer:

```bash
lotus wallet approve \
  <approveAddress> \
  <multisigAddress> \
  <transferID>
```

| Parameter | Description |
|-----------|-------------|
| `<approveAddress>` | The approver's wallet address (a different signer) |
| `<multisigAddress>` | The multi-sign address |
| `<transferID>` | The proposal ID from Step 2 output |

#### Step 4: Verify the change

```bash
# Check the owner has been updated
lotus-miner info

# Output should show:
# Owner: t2xxxxxxxx... (multisig)
# Worker: t1yyyyyy...
```

---

### 2. Multi-Sign Address → Different Multi-Sign Address

If you need to change signers or threshold (e.g., rotate keys or update team membership):

#### Step 1: Create the new multi-sign address

```bash
# Create a new multi-sign address with updated signers
lotus msig create --required=2 <newsigner1> <newsigner2> <newsigner3>
# → t2newMultisigAddress
```

#### Step 2: Propose the owner change (from the **old** multi-sign)

```bash
# Proposer must be a signer of the OLD multi-sign address
lotus-miner actor-msig set-owner \
  --really-do-it=true \
  --from=<proposerAddress> \
  <newMultisigAddress> \
  <oldMultisigAddress>
```

| Parameter | Description |
|-----------|-------------|
| `--from=<proposerAddress>` | A signer of the **old** multi-sign address |
| `<newMultisigAddress>` | The **new owner** address |
| `<oldMultisigAddress>` | The current owner multi-sign address (for authorization) |

#### Step 3: Approve the proposal

```bash
# Another signer of the OLD multi-sign address approves
lotus wallet approve \
  <approveAddress> \
  <oldMultisigAddress> \
  <transferID>
```

#### Step 4: Second round — Propose from the new multi-sign

```bash
lotus-miner actor-msig set-owner \
  --really-do-it=true \
  --from=<proposerAddress> \
  <newMultisigAddress> \
  <newMultisigAddress>
```

#### Step 5: Approve the second proposal

```bash
lotus wallet approve \
  <approveAddress> \
  <newMultisigAddress> \
  <transferID>
```

---

### 3. Multi-Sign Address → Single-Sign (Ordinary) Address

If you need to revert back to a single-signer owner:

#### Step 1: Prepare the ordinary address

```bash
# Create a new wallet (or use an existing one)
lotus wallet new bls
# → t1ordinaryAddress
```

#### Step 2: Propose the change

```bash
# From a signer of the multi-sign address
lotus-miner actor-msig set-owner \
  --really-do-it=true \
  --from=<proposerAddress> \
  <t1ordinaryAddress> \
  <multisigAddress>
```

#### Step 3: Approve

```bash
lotus wallet approve \
  <approveAddress> \
  <multisigAddress> \
  <transferID>
```

> **⚠️ Warning**: This removes multi-sign protection from your owner address. Only do this temporarily during maintenance, and switch back to multi-sign when done.

---

## Common Operations with Multi-Sign Owner

Once your owner is a multi-sign address, all sensitive operations require the multi-sign workflow.

### 1. Withdrawing Balance

To withdraw FIL from your miner when the owner is a multi-sign address:

#### Step 1: Propose the withdrawal

```bash
lotus-miner actor-msig withdraw \
  --from=<proposerAddress> \
  <amount>
```

| Parameter | Description |
|-----------|-------------|
| `--from=<proposerAddress>` | A signer of the owner multi-sign address (proposer) |
| `<amount>` | Amount to withdraw (in FIL or attoFIL) |
| `--minerid` | (Optional) Miner ID, uses default if not set |

#### Step 2: Calculate the required approval

The withdraw command generates a transfer ID. Note it from the output.

#### Step 3: Approve

```bash
lotus wallet approve \
  <approveAddress> \
  <multisigAddress> \
  <transferID> \
  [proposerAddress destination value [methodId methodParams]]
```

| Parameter | Description |
|-----------|-------------|
| `<approveAddress>` | A **different** signer of the multi-sign address |
| `<multisigAddress>` | The owner multi-sign address |
| `<transferID>` | ID from Step 1 |
| `proposerAddress` | (Optional) Original proposer's address |
| `destination` | (Optional) Where the funds go |
| `value` | (Optional) Amount |
| `methodId`/`methodParams` | (Optional) Method identifiers |

> **💡 Tip**: Most withdrawals only need `<approveAddress>`, `<multisigAddress>`, and `<transferID>`. The optional parameters are for complex proposals.

---

### 2. Modifying Control Addresses

Control addresses are authorized to sign WindowPoST proofs and other operational messages.

#### Step 1: Propose the control address change

```bash
lotus-miner actor-msig control set \
  --really-do-it=true \
  --from=<proposerAddress> \
  <address1> <address2> ...
```

| Parameter | Description |
|-----------|-------------|
| `--from=<proposerAddress>` | A signer of the owner multi-sign address |
| `<addresses>` | New set of control addresses (replaces existing) |

#### Step 2: Approve

```bash
# Another signer must approve
lotus wallet approve \
  <approveAddress> \
  <multisigAddress> \
  <transferID>
```

#### Step 3: Verify

```bash
lotus-miner actor control list
```

---

### 3. Modifying Worker Address

The worker address submits WindowPoST proofs and performs day-to-day operations. Changing it when the owner is a multi-sign address requires a **two-phase process** (propose → wait → confirm).

#### Phase 1: Propose the change

```bash
# Step 1a: Propose new worker address
lotus-miner actor-msig propose-change-worker \
  --really-do-it=true \
  --from=<proposerAddress> \
  <newWorkerAddress>
```

| Parameter | Description |
|-----------|-------------|
| `--from=<proposerAddress>` | A signer of the owner multi-sign address |
| `<newWorkerAddress>` | The new worker address |

#### Step 1b: Approve the proposal

```bash
lotus wallet approve \
  <approveAddress> \
  <multisigAddress> \
  <transferID>
```

#### Step 2: Wait for the delay period

The worker change is **not immediate**. It requires waiting approximately **900 block epochs** (~7.5 hours at 30-second block times).

```bash
# Check current height
lotus chain head

# Calculate target height (current + 900)
# Wait until you see the target height reached
```

#### Phase 3: Confirm the change

After the delay period has elapsed:

```bash
# Step 3a: Confirm the worker change
lotus-miner actor-msig confirm-change-worker \
  --really-do-it=true \
  --from=<proposerAddress> \
  <newWorkerAddress>
```

#### Step 3b: Approve the confirmation

```bash
lotus wallet approve \
  <approveAddress> \
  <multisigAddress> \
  <transferID>
```

#### Step 4: Verify

```bash
lotus-miner actor control list
# Check that the worker address has been updated
```

---

## Workflow Summary

### Quick Reference: Multi-Sign Operations

```text
┌─────────────────────────────────────────────────────────────────┐
│              MULTI-SIGN WORKFLOW REFERENCE                       │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│  CREATE MULTI-SIGN ADDRESS                                       │
│  lotus msig create --required=2 <addr1> <addr2> <addr3>          │
│                                                                  │
│  CHANGE OWNER: Normal → Multi-Sign                               │
│  1. lotus-miner actor-msig set-owner --really-do-it=true         │
│     --from=<signer> <msig> <msig>                                │
│  2. lotus wallet approve <signer2> <msig> <transferID>           │
│                                                                  │
│  CHANGE OWNER: Multi-Sign → Multi-Sign                           │
│  1. lotus-miner actor-msig set-owner ... <newMsig> <oldMsig>    │
│  2. lotus wallet approve <signer2> <oldMsig> <txID>              │
│  3. lotus-miner actor-msig set-owner ... <newMsig> <newMsig>   │
│  4. lotus wallet approve <signer2> <newMsig> <txID>              │
│                                                                  │
│  WITHDRAW (Multi-Sign Owner)                                     │
│  1. lotus-miner actor-msig withdraw --from=<signer> <amount>    │
│  2. lotus wallet approve <signer2> <msig> <transferID>           │
│                                                                  │
│  CHANGE CONTROL ADDRESSES (Multi-Sign Owner)                     │
│  1. lotus-miner actor-msig control set --really-do-it=true       │
│     --from=<signer> <addr1> <addr2>                              │
│  2. lotus wallet approve <signer2> <msig> <transferID>           │
│                                                                  │
│  CHANGE WORKER (Multi-Sign Owner) — 3-phase                     │
│  Phase 1: propose-change-worker + approve                        │
│  Phase 2: ⏳ wait 900 epochs (~7.5 hours)                       │
│  Phase 3: confirm-change-worker + approve                        │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

### Operation Decision Flow

```text
Which multi-sign operation do you need?
│
├─ Change owner type?
│  ├─ Normal → Multi-Sign    → 1 proposal + 1 approval
│  ├─ Multi-Sign → Multi-Sign → 2 rounds (propose + approve × 2)
│  └─ Multi-Sign → Normal    → 1 proposal + 1 approval
│
├─ Withdraw FIL?
│  └─ 1 proposal + 1 approval
│
├─ Change control addresses?
│  └─ 1 proposal + 1 approval
│
└─ Change worker address?
   └─ Phase 1: propose + approve (immediate)
      └─ Phase 2: wait 900 epochs
         └─ Phase 3: confirm + approve
```

---

## Security Considerations

### Best Practices

1. **Use different machines for different signers**
   - Don't store all multi-sign keys on one computer
   - Distribute signers across team members or hardware wallets

2. **Set an appropriate threshold**
   - 2-of-3: Best balance of security and operability
   - 3-of-5: Maximum security (lose 2 keys before compromised)
   - Avoid 2-of-2: If one key is lost, you lose access entirely

3. **Regular key rotation**
   - Update multi-sign signers when team members change
   - Rotate keys if any signer machine is compromised

4. **Test on Calibration network first**
   - Practice the workflow on the test network before mainnet
   - Filecoin Calibration network: `--calibnet` flag

5. **Monitor multi-sign proposals**
   ```bash
   # Check pending proposals for your multi-sign address
   lotus msig inspect <multisigAddress>
   ```

### Risks

| Risk | Impact | Mitigation |
|------|--------|------------|
| Lost all signer keys | Permanent loss of miner control | Keep at least one key in cold storage |
| Threshold too high | Can't get enough approvals (operational delay) | Use 2-of-3, not 3-of-3 |
| Gas costs | Each proposal and approval costs FIL | Keep extra FIL in signer wallets |
| Phishing | Fake proposal approvals | Verify each approval's `transferID` |

---

## Troubleshooting

### ❌ "Not a signer" error when proposing

```
Error: signer <address> is not a signer of multisig
```

**Fix**: The `--from` address must be one of the multi-sign address's signers.
```bash
# Check who the signers are
lotus msig inspect <multisigAddress>
```

### ❌ Transaction never executes after approval

**Fix**: Check if enough approvals have been collected:
```bash
# Inspect pending transactions
lotus msig inspect --vesting <multisigAddress>
# Check if threshold has been met
```

### ❌ Worker change delay not working

```
Error: worker change not yet ready
```

**Fix**: The 900-epoch delay hasn't elapsed yet.
```bash
# Check when the proposal was made
lotus chain gettipset @<proposalEpoch>
# Current height must be >= proposalEpoch + 900
```

### ❌ "Insufficient funds" for proposal

**Fix**: The multi-sign address itself needs FIL for gas.
```bash
# Send FIL to the multi-sign address
lotus send <multisigAddress> <amount>
```

---

## References

- [Lotus Multi-Signature Documentation](https://lotus.filecoin.io/storage-providers/operate/addresses/#multi-signature-addresses)
- [Filecoin Msig Actor Specification](https://spec.filecoin.io/systems/filecoin_vm/sysactors/msig/)
- [Issue #298: Local Multi Sign Wallet](https://github.com/filecoin-project/community/issues/298)

---

*This guide is part of the Filecoin Storage Provider Bounty Program. For corrections or updates, please open a PR or issue.*

*Part of the [Storage Provider Bounty Program](https://github.com/filecoin-project/community/blob/main/storage-provider-bounty-program/README.md)*
