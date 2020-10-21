# Filecoin Security

Having a vibrant community of security researchers auditing Filecoin and its dependencies is at the core of building a robust platform, mitigating risks and building trust in the Filecoin ecosystem. We invite security researchers acting in good faith to help us maintain a high standard of security.

This includes encouraging responsible vulnerability research and disclosure. This document sets out our definition of good faith in the context of finding and reporting vulnerabilities, our security procedure, and the bug bounty program.

For additional details and updates on Filecoin Security or the Bug Bounty Program - head over to the [Filecoin Security website](https://security.filecoin.io). 

## Vulnerability Reporting

Almost anything you find that is a bug in the codebase should be filed as an issue on Github. The exception is if you find a security vulnerability. If you discover a security issue, please bring it to our attention right away. We’ve created two main channels for reporting:

1. Sending an email to [security@filecoin.org](mailto:security@filecoin.org). Use our [PGP key](https://github.com/filecoin-project/community/blob/master/public.key) to encrypt sensitive information.
1. Request to join the **filecoin_sec** team on [Keybase](http://keybase.io), where we can set up a private channel to discuss.

Please **DO NOT** file a public issue or discuss the vulnerability in public places like Slack, Twitter, etc. See our Disclosure Policy below to learn more about sharing details about vulnerabilities that have been found.

## Security Audits and Updates

Protocol implementations have undergone third-party Security Audits. They are linked in the Filecoin Specification under [Implementation Status](https://spec.filecoin.io/#intro__implementations-status).

## Bug Bounty Program

Reported security vulnerabilities will be eligible for a bounty based on severity, calculated based on their Impact and Likelihood using the [OWASP Risk Rating model](https://owasp.org/www-community/OWASP_Risk_Rating_Methodology).

The following point ranges will be assigned based on Severity:

- Critical: up to 25,000 points
- High: up to 15,000 points
- Medium: up to 10,000 points
- Low: up to 2,000 points
- Note: up to 500 points

Currently, 1 point = 1 USD.

Higher rewards will also be paid to reported vulnerabilities that offer quality written descriptions, test code, scripts and detailed instructions, and well-documented fixes.

Evaluation of the significance of the vulnerability and specific bounty amount assigned is at the sole discretion of the Filecoin Security Team, which consists of core developers and contributors.

### Ground Rules

We encourage good-faith security research and ask that you follow these guidelines to avoid any confusion between legitimate research and malicious attack, we ask that you attempt, in good faith, to:

- Testing must not violate any law or compromise any data that is not yours. Please refrain from the following:
  - Denial of Service attacks and active exploits against the Filecoin network or Filecoin miners and nodes
  - Social engineering and phishing of Filecoin project contributors, contractors, ecosystem collaborators or community members
  - Physical or electronic attempts to access offices where project contributors work or data centers where Filecoin nodes are located
  - Compromising user accounts or stealing funds
- Report any vulnerability you’ve discovered promptly
- Help us improve this security process as it is critical to our mission by suggesting improvements.
- Avoid violating the privacy of Filecoin users and community members, disrupting their systems, destroying data, stealing funds and/or harming the user experience
- Perform testing only on in-scope systems, and respect systems and activities which are out-of-scope
- Interact only with test accounts you own or with explicit permission from the account holder
- If a vulnerability provides unintended access to data: Limit the amount of data you access to the minimum required for effectively demonstrating a Proof of Concept; and cease testing and submit a report immediately
- Play by the rules. This includes following this policy as well as any other relevant agreements
- Use only the Official Channels to discuss vulnerability information with us
- Handle the confidentiality of details of any discovered vulnerabilities according to our Disclosure Policy

### Safe Harbor

When conducting vulnerability research according to this policy, we consider this research conducted under this policy to be:

- Authorized in view of any applicable anti-hacking laws, and we will not initiate or support legal action against you for accidental, good faith violations of this policy
- Authorized in view of relevant anti-circumvention laws, and we will not bring a claim against you for circumvention of technology controls
- Exempt from restrictions in our Acceptable Usage Policy that would interfere with conducting security research, and we waive those restrictions on a limited basis
- Lawful, helpful to the overall security of the Internet, and conducted in good faith

You are expected to comply with all applicable laws. If legal action is initiated by a third party against you and you have complied with this policy, we will take steps to make it known that your actions were conducted in compliance with this policy.

If at any time you have concerns or are uncertain whether your security research is consistent with this policy, please submit a report through one of our Official Channels before going any further.

### Scope

In scope for our Bug Bounty program are vulnerabilities in the core protocol, protocol implementations, and some supporting libraries that may be widely used by developers. These include the following repos, but not only:

- Lotus Core
  - [filecoin-project/lotus](https://github.com/filecoin-project/lotus)
- Markets
  - [filecoin-project/go-fil-markets](https://github.com/filecoin-project/go-fil-markets)
  - [ipfs/go-graphsync](https://github.com/ipfs/go-graphsync)
- Storage Miner
  - [filecoin-project/lotus/tree/master/miner](https://github.com/filecoin-project/lotus/tree/master/miner)
- Actors
  - [filecoin-project/specs-actors](https://github.com/filecoin-project/specs-actors)
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
