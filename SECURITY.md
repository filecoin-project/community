# Filecoin Security

Having a vibrant community of security researchers auditing Filecoin and its dependencies is at the core of building a robust platform, mitigating risks and building trust in the Filecoin ecosystem. We invite security researchers acting in good faith to help us maintain a high standard of security.

This includes encouraging responsible vulnerability research and disclosure. This document sets out our definition of good faith in the context of finding and reporting vulnerabilities, our security procedure, and the bug bounty program.

For additional details and updates on Filecoin Security or the Bug Bounty Program - head over to the [Filecoin Security website](https://security.filecoin.io). 

## Vulnerability Reporting

Almost anything you find that is a bug in the codebase should be filed as an issue on Github. The exception is if you find a security vulnerability. If you discover a security issue, please bring it to our attention right away. We’ve created two main channels for reporting:

1. Sending an email to [security@filecoin.org](mailto:security@filecoin.org). Use our [key](https://github.com/filecoin-project/community/blob/master/public.key) to encrypt sensitive information.
1. Request to join the **filecoin_sec** team on [Keybase](http://keybase.io), where we can set up a private channel to discuss.

Please **DO NOT** file a public issue or discuss the vulnerability in public places like Slack, Twitter, etc. See our Disclosure Policy below to learn more about sharing details about vulnerabilities that have been found.

## Security Audits and Updates

Protocol implementations have undergone third-party Security Audits. They are linked in the Filecoin Specification under [Implementation Status](https://spec.filecoin.io/#intro__implementations-status).

## Bug Bounty Program

Reported security vulnerabilities will be eligible for a Bug Bounty based on Severity, calculated based on its Impact and Likelihood using the [OWASP Risk Rating model](https://owasp.org/www-community/OWASP_Risk_Rating_Methodology).

The following is a guide for how points may be allocated to issues reported based on severity:

  - Critical: up to 500,000 points
  - High: up to 100,000 points
  - Medium: up to 25,000 points
  - Low: up to 10,000 points
  - None: up to 5,000 points

Where currently 1 point = 1 USD (payable in USD, DAI or FIL).

Higher rewards will also be paid to reported vulnerabilities that offer quality written descriptions, test code, scripts and detailed instructions, and well-documented fixes.

Evaluation of the significance of the vulnerability and specific bounty amount assigned is at the sole discretion of the Filecoin Security Team, which consists of core developers and contributors.


> <small>NOTE: Reporters are responsible for all taxes and all awards subject to applicable law.</small>
> <small>We are not able to pay bounty awards to individuals who are on a U.S. sanctions list or in a country on a U.S. sanctions list.</small>


#### Scope (now includes reports for the FEVM implementation)

In scope for our Bug Bounty program are vulnerabilities in the core protocol and protocol implementations that have been security audited:

|Category      |Level   |Impact In Scope                                                                                                  |
|--------------|--------|--------------------------------------------------------------------------------------------------------|
|<div style="width:180px">**Blockchain/DLT**</div>|<div style="width:200px"><nobr>**Critical(POC required)**</nobr></div>|Network not being able to confirm new transactions (Total network shutdown)                             |
|              |        |Unintended permanent chain split requiring hard fork (Network partition requiring hard fork)            |
|              |        |Direct loss of funds                                                                                    |
|              |        |Permanent, repeatable freezing of funds affecting core protocol areas (fix requires hard fork)          |
|              |        |RPC API crash capable of impacting block production                                                     |
|              |        |Protocol-level bug causing breakage of all contracts deployed on the chain                              |
|              |        |Protocol-level bug that enables tricking contracts into sending funds to arbitrary addresses            |
|              |**High(POC required)**    |Unintended chain split (Network partition) with localized impacts                    |
|              |        |Transient consensus failures                                                                            |
|              |        |Inability to propagate new transactions                                                                 |
|              |        |Protocol-level bug preventing contracts from using their funds                                          | 
|              |        |Protocol-level bug causing the inability for developers to deploy new smart contracts                   |
|              |        |Protocol-level bug rendering a single contract unusable after the exploit (i.e. contract bricked)       |
|              |**Medium**  |High compute consumption by validator/mining nodes                                                  |
|              |        |Attacks against thin clients                                                                            |
|              |        |DoS of greater than 30% of validator or miner nodes and does not shut down the network                  |
|              |        |EVM instruction fails to execute, in a general way                                                      |
|              |        |Inability to deploy a contract under a specific circumstances                                           |
|              |**Low** |DoS of greater than 10% but less than 30% of validator or miner nodes and does not shut down the network|
|              |        |Underpricing transaction fees relative to computation time                                              |
|              |        |Contract on the platform fails to deliver promised returns, but doesn’t lose values                                              |
|              |        |EVM instruction fails to execute when provided with concrete parameters                                 |

- **Important notice for the issue criteria that is presented in the table:**
  - Security reports that are not explicitly listed in the table will still be reviewed and matched up against the severity classification based on their impact.

  <br>

- FVM
  - Reference FVM (ref-fvm)
    - Reference implementation of the Filecoin VM ([Repository](https://github.com/filecoin-project/ref-fvm)).
- Lotus Core
  - [filecoin-project/lotus](https://github.com/filecoin-project/lotus)
- Markets
  - [filecoin-project/boost](https://github.com/filecoin-project/boost)
  - [ipfs/go-graphsync](https://github.com/ipfs/go-graphsync)
- Storage Miner
  - [filecoin-project/lotus/tree/master/miner](https://github.com/filecoin-project/lotus/tree/master/miner)
- Actors
  - [filecoin-project/builtin-actors](https://github.com/filecoin-project/builtin-actors)
- Proofs
  - [filecoin-project/rust-fil-proofs-ffi](https://github.com/filecoin-project/rust-fil-proofs-ffi)
  - [filecoin-project/rust-filecoin-proofs-api](https://github.com/filecoin-project/rust-filecoin-proofs-api)
  - [filecoin-project/rust-fil-proofs](https://github.com/filecoin-project/rust-fil-proofs)
    - [filecoin-project/bellman/](https://github.com/filecoin-project/bellman/)
    - [filecoin-project/merkle_light](https://github.com/filecoin-project/merkle_light)
    - [filecoin-project/neptune](https://github.com/filecoin-project/neptune)
    - [filecoin-project/neptune-triton](https://github.com/filecoin-project/neptune-triton)
    - [filecoin-project/paired](https://github.com/filecoin-project/paired)
- Dependencies
  - [filecoin-project/go-address](https://github.com/filecoin-project/go-address)
  - [filecoin-project/go-amt-ipld](https://github.com/filecoin-project/go-amt-ipld)
  - [filecoin-project/go-bitfield](https://github.com/filecoin-project/go-bitfield)
  - [filecoin-project/go-cbor-util](https://github.com/filecoin-project/go-cbor-util)
  - [filecoin-project/go-crypto](https://github.com/filecoin-project/go-crypto)
  - [filecoin-project/go-data-transfer](https://github.com/filecoin-project/go-data-transfer)
  - [filecoin-project/go-fil-commcid](https://github.com/filecoin-project/go-fil-commcid)
  - [filecoin-project/go-padreader](https://github.com/filecoin-project/go-padreader)
  - [filecoin-project/go-sectorbuilder](https://github.com/filecoin-project/go-sectorbuilder)
  - [filecoin-project/go-statemachine](https://github.com/filecoin-project/go-statemachine)
  - [filecoin-project/go-statestore](https://github.com/filecoin-project/go-statestore)
  - [ipfs/go-hamt-ipld](https://github.com/ipfs/go-hamt-ipld)
  - [ipfs/go-ipld-cbor](https://github.com/ipfs/go-ipld-cbor)
  - [whyrusleeping/cbor-gen](https://github.com/whyrusleeping/cbor-gen)

<small>* Implementations undergoing active development that have not yet been security audited are currently not in scope.</small>

#### Read More

- Visit the <a href="https://spec.filecoin.io/#intro__implementations-status" target="_blank">Filecoin Spec: Implementation Status</a> for more information about these projects and their audits.

- [Filecoin Improvement Proposals(FIPs)](https://github.com/filecoin-project/FIPs/tree/master/FIPS)

### Out of Scope

- Filecoin websites and Filecoin infrastructure in general are not part of the bug bounty program.
- Third-party services and websites that show information about the Filecoin network (block explorers, stats dashboards, price indicators, miner leaderboards, etc.) are also out of scope.
- Vulnerabilities previously submitted by another person or identified in a published audit report are not eligible for bug bounty rewards.
- Public disclosure of a vulnerability makes it ineligible for a bug bounty.

Filecoin’s core development team, employees of Protocol Labs, the Filecoin Foundation and others paid by these organizations to work on the Filecoin project, indirectly or directly, are not eligible for bug bounty rewards.

### Disclosure Policy

We have a **Coordinated Disclosure policy**.  A researcher can share details of a vulnerability after a fix has been applied and our security team has provided permission to disclose. We will make a best effort to address and patch (if possible) all vulnerabilities within 90 days from submission. Please keep security vulnerabilities private until we have had a chance to address them.

If you have filed an issue and are interested in options for disclosing it, please reach out to us at security@filecoin.org.

### Expectations

When working with us according to this policy, you can expect us to:

- Work with you to understand and validate your report, including a timely initial response to the submission
- Work to remediate discovered vulnerabilities in a timely manner
- Recognize your contribution to improving our security if you are the first to report a unique vulnerability, and your report triggers a code or configuration change.

### Response Process

1. A security researcher reports a vulnerability via email to security@filecoin.org or Keybase.
1. Our security team will designate a Response Manager in charge of a particular report based on expertise and availability. They will acknowledge receipt of the report in a quick response to the researcher.
1. The Response Manager will evaluate the vulnerability and assign an initial OWASP Severity estimate. They may optionally also contact the researcher using a secure private channel for more information.
1. Based on the vulnerability’s potential OWASP Severity additional security team members will be alerted for additional review and to develop a patch.
    1. Response Manager designates a private git branch for the patch + proposed OWASP score
    1. Reviewed by security team
    1. Response Manager drafts vulnerability announcement for the community
        1. Severity - Systems impacted - Solutions / patches
    1. Security team discusses a release target + date for the announcement + patch
    1. Response Manager communicates with the researcher who submitted the vulnerability:
        1. Proposed patch + release date
        1. Whether the researcher would like public credit for reporting the bug (anonymous reporting is also supported)
        1. Reporter’s bounty distribution address
    1. The security team will make a best effort to complete the above process within 90 days.
1. Community notifications and patches
    1. For High or Critical Severity issues, the security team will notify the Filecoin community that a security release is imminent. Notifications can include Filecoin Community Slack announcements, tweets, emails to ecosystem collaborators. 
        1. 24 hours following this notification, the fixes are applied publicly and new releases are issued.
    1. Medium to High Severity issues may result in a minor release including the patch.
    1. Low severity issues can be addressed in the next regular release.

### Legal considerations

Reporters are responsible for all taxes and all awards subject to applicable law.

We are not able to pay bounty awards to individuals who are on a U.S. sanctions list or in a country on a U.S. sanctions list.
