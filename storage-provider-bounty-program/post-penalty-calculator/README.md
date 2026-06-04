# PoST Penalty Calculator

> An interactive tool to estimate Filecoin storage provider penalties for missed WindowPoST deadlines.

## Usage

Simply open `index.html` in any modern web browser. No server or installation required.

## Features

- **Miner Configuration**: Input your power, sector size, number of faulty sectors, and duration
- **Network Parameters**: Configurable network power, block reward, and FIL price
- **Preset Scenarios**: Quick-switch between current, conservative, bull, and bear market values
- **Real-time Results**: Instant penalty calculations update as you type
- **Detailed Breakdown**: See the full formula applied step by step
- **Termination Fee**: Estimate worst-case scenario (sector termination)
- **Balance Recommendation**: Get a suggested minimum FIL balance for 7 days of coverage

## Formula

The calculator implements the Filecoin protocol fault fee formula:

1. **Sector Power Fraction** = sectorSize / networkTotalPower
2. **Expected Daily Reward per Sector** = dailyBlockReward × sectorPowerFraction
3. **Daily Fault Fee** = faultySectors × sectorReward × 1.5
4. **Termination Fee** = sectorReward × 20 per sector

## Sources

- [Filecoin Specification — Faults](https://spec.filecoin.io)
- [Lotus Documentation](https://lotus.filecoin.io)
- [spacegap.github.io](https://spacegap.github.io)

---

*Part of the Filecoin Storage Provider Bounty Program (#272)*
