**Background**
The purpose of this poll is to determine community consensus to accept or reject [FIP0036](https://github.com/filecoin-project/FIPs/blob/master/FIPS/fip-0036.md).

Discussions and further questions related to this FIP should be directed to the [active discussion thread](https://github.com/filecoin-project/FIPs/discussions/453).

> You can find more governance details [here](https://github.com/filecoin-project/FIPs/discussions/464).
> See the **How to sign a vote on FilPoll using Lotus/Glif** [here](https://pl-strflt.notion.site/WIP-How-to-sign-a-vote-on-FilPoll-using-Lotus-Glif-95d9b0a32f9c48858574f9cb072c054b).

**Proposal**
* Increase minimum sector duration time from six months to 1 year
* Increase the maximum sector duration time from 1.5 years to 3.5 years
* Introduce a Sector Duration Multiplier for all sectors, regardless of deal type
* Increase Sector Initial Consensus Pledge from 30% to 50%

All participating community members are encouraged to review the terms of the FIP in entirety prior to casting a vote.

**Impact**
FIP0036 intends to introduce more favorable locked value dynamics, which will contribute to overall network utility, stable circulating supply dynamics, and SP profitability and optionality.

For more more detailed information, see the [FIP impact analysis and summary](https://pl-strflt.notion.site/Duration-Changes-FIP-discussion-Analysis-Summary-735ce6685b7946f0a03fc13c3fe271fa).

For additional details related to impact modeling and FIP draft iteration, see [this updated comment and analysis](https://pl-strflt.notion.site/Duration-FIP-revisions-7426f344685940409ac513a0ffcccc86) from FIP authors.

> Note: Core Devs have already confirmed that, if accepted, FIP0036 will be scheduled for inclusion in the network v17 upgrade.

**Note**
During the vote process, real-time results on Fil Poll will be publicly available. However, to ensure that the voting process remains secure and robust, votes will be organized and weighted within the following categories:
1. Storage Providers who make storage deals (vote weighted by deal bytes)
2. Storage Providers who provide storage capacity (weighted by raw bytes)
3. Storage Clients (weighted by deal bytes)
4. Token Holders (weighted by FIL balance for both regular and multisig wallets)
5. Core Devs (weighted by headcount)

Data processing will be immediate and fully transparent. The model used for post processing data will be made available, as will all raw polling data. Each vote received will be matched to the appropriate subset of the 5 announced categories and weighted accordingly.

Detailed information about the voting and governance processes can be found [here](https://github.com/filecoin-project/FIPs/discussions/464).

---
Options:
- **< Approve >**: < I approve FIP0036 >
- **< Reject >**: < I reject FIP0036 >

---
start: 2022-09-14 22:00
end: 2022-09-28 22:00
constituents: [ storageminers | tokenholders | coredevs ]
author: @AxCortesCubero @jbenet @misilva73 @momack2 @tmellan @vkalghatgi @zixuanzh
discussion: https://github.com/filecoin-project/FIPs/discussions/453
