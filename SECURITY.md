# Filecoin Security

Having a vibrant community of security researchers auditing Filecoin and its dependencies is at the core of building a robust platform, mitigating risks, and building trust in the Filecoin ecosystem. We invite security researchers acting in good faith to help us maintain a high standard of security.

This includes encouraging responsible vulnerability research and disclosure. This document sets out our definition of good faith in the context of finding and reporting vulnerabilities, our security procedure, and the bug bounty program.

For additional details and updates on Filecoin Security or the Bug Bounty Program, visit the [Filecoin Security website](https://fil.org/security).

## Vulnerability Reporting

Almost anything you find that is a bug in the codebase should be filed as an issue on GitHub. The exception is if you find a **security vulnerability**.

**If you discover a security issue, please report it immediately:**

### Primary Reporting Method

**Report via Immunefi Bug Bounty Program:** [https://immunefi.com/bug-bounty/filecoin/information/](https://immunefi.com/bug-bounty/filecoin/information/)

This is the recommended and primary method for all security vulnerability reports.

### Alternative Reporting Methods

For security-related questions or if you cannot use Immunefi:
- Email: [security@fil.org](mailto:security@fil.org) (use PGP encryption for sensitive information)

### What NOT to Do

Please **DO NOT**:
- File a public issue on GitHub for security vulnerabilities
- Discuss the vulnerability in public places like Slack, Twitter/X, or other social media
- Disclose the vulnerability publicly before receiving permission from our security team

See our [Coordinated Disclosure Policy](https://fil.org/security/coordinated-disclosure-policy) for details about responsible disclosure.

## Security Audits and Updates

Protocol implementations undergo third-party security audits. Security updates and audit reports are available on the [Filecoin Specs]([https://fil.org/security](https://spec.filecoin.io/#section-appendix.audit_reports)).

For the latest security updates and announcements, visit our [Security Updates page](https://fil.org/security).

## Bug Bounty Program

Filecoin's bug bounty program is hosted on **Immunefi**, offering rewards up to **$150,000 USD** for critical vulnerabilities. Since 2020, Filecoin has worked with 100+ top security researchers and rewarded more than $650,000 in bounties.

**Visit the program:** [https://immunefi.com/bounty/filecoin/](https://immunefi.com/bounty/filecoin/)

### Reward Structure

Rewards are based on the severity and impact of the vulnerability:

- **Critical**: Up to $150,000 USD (minimum $100,000 for critical blockchain/DLT bugs)
- **High**: Determined based on impact and likelihood
- **Medium**: Determined based on impact and likelihood
- **Low**: Determined based on impact and likelihood

All rewards are paid in USD/USDC by the Filecoin Foundation and are scaled based on:
- Ease of exploitation
- Impact of the bug
- Likelihood of the vulnerability
- Quality of the report

**Proof of Concept (PoC) is required for all severity levels.** Higher rewards are paid to reports that include quality written descriptions, test code, scripts, detailed instructions, and well-documented fixes.

### In Scope

The bug bounty program covers vulnerabilities in (non-exhaustive):
- Lotus, 
- builtin-actors 
- FVM
- F3

For the complete and up-to-date list of in-scope assets and impacts, please refer to the [Immunefi program page](https://immunefi.com/bounty/filecoin/).

### Out of Scope

- Filecoin websites and infrastructure (unless explicitly listed as in-scope on Immunefi)
- Third-party services (block explorers, stats dashboards, price indicators, miner leaderboards)
- Vulnerabilities previously submitted by another person or identified in published audit reports
- Public disclosure of a vulnerability makes it ineligible for a bug bounty
- Vulnerabilities that don't meet the in-scope impact criteria on Immunefi

**Eligibility:** Current and former members of the Filecoin core development team, employees/contractors of Protocol Labs or the Filecoin Foundation, and anyone paid (directly or indirectly) to work on the Filecoin project are not eligible for bug bounty rewards.

## Ground Rules

We encourage good-faith security research and ask that you follow these guidelines:

**DO:**
- Comply with all applicable laws
- Report any vulnerability you've discovered promptly
- Follow responsible disclosure practices
- Provide detailed reports with PoC where applicable
- Use only official reporting channels
- Test only on in-scope systems with proper authorization
- Interact only with test accounts you own or have explicit permission to use

**DO NOT:**
- Conduct Denial of Service (DoS) attacks or active exploits against the Filecoin network, miners, or nodes
- Engage in social engineering or phishing of Filecoin project contributors or community members
- Attempt physical or electronic access to offices or data centers
- Compromise user accounts or steal funds
- Violate privacy of users or community members
- Destroy data or harm user experience
- Access more data than necessary to demonstrate a PoC
- Publicly disclose vulnerabilities before receiving permission

## Safe Harbor

When conducting vulnerability research according to this policy, we consider this research to be:

- **Authorized** in view of any applicable anti-hacking laws, and we will not initiate or support legal action against you for accidental, good-faith violations of this policy
- **Authorized** in view of relevant anti-circumvention laws, and we will not bring a claim against you for circumvention of technology controls
- **Exempt** from restrictions in our Acceptable Usage Policy that would interfere with conducting security research
- **Lawful**, helpful to the overall security of the Internet, and conducted in good faith

You are expected to comply with all applicable laws. If legal action is initiated by a third party against you and you have complied with this policy, we will take steps to make it known that your actions were conducted in compliance with this policy.

If at any time you have concerns or are uncertain whether your security research is consistent with this policy, please contact us at [security@fil.org](mailto:security@fil.org) before going any further.

## Coordinated Disclosure Policy

Filecoin Foundation follows a **Coordinated Disclosure Policy** to honor security researcher contributions while protecting the network and its participants.

**When You Can Publish:** Researchers can publish information about their bug reports after:
1. The bug has been fixed
2. The researcher has been paid
3. Network participants have had time to upgrade to the patched version
4. You receive permission from the security team

We follow **Immunefi's Publication Category 1: Transparent**, which allows responsible disclosure after these conditions are met.

**Timeline:** We aim to address and patch all vulnerabilities within **90 days** from submission.

**For complete details**, including the full process, publication guidelines, and Safe Harbor provisions, visit our [Coordinated Disclosure Policy](https://fil.org/security/coordinated-disclosure-policy).

## Response Process

When you report a vulnerability, here's what happens:

1. **Report Submission** → Submit via [Immunefi](https://immunefi.com/bug-bounty/filecoin/information/).
2. **Acknowledgment** → Response Manager acknowledges receipt promptly
3. **Evaluation** → Vulnerability is assessed and severity assigned
4. **Remediation** → Security team develops and reviews patch
5. **Communication** → You receive updates on patch timeline, credit options, and bounty details
6. **Resolution** → Patch is released and bounty is processed

**Community Notifications:**
- **High/Critical**: Community notified 24 hours before patch release
- **Medium**: May result in a minor release
- **Low**: Addressed in next regular release

For detailed response procedures, visit our [Coordinated Disclosure Policy](https://fil.org/security/coordinated-disclosure-policy).

## Additional Resources

- **Filecoin Security Hub**: [https://fil.org/security](https://fil.org/security)
- **Bug Bounty Program**: [https://immunefi.com/bounty/filecoin/](https://immunefi.com/bounty/filecoin/)
- **Coordinated Disclosure Policy**: [https://fil.org/security/coordinated-disclosure-policy](https://fil.org/security/coordinated-disclosure-policy)
- **Web3 Security Maturity Model**: [https://fil.org/security/maturity-model](https://fil.org/security/maturity-model)
- **Security Contact**: [security@fil.org](mailto:security@fil.org)
- **Audit Inquiries**: [audits@fil.org](mailto:audits@fil.org)

## Legal Considerations

- Reporters are responsible for all taxes, and all awards are subject to applicable law
- We are not able to pay bounty awards to individuals who are on a U.S. sanctions list or in a country on a U.S. sanctions list
- The Filecoin Security Team, consisting of core developers and contributors, evaluates the significance of reported vulnerabilities and appropriate bounty awards in its sole discretion
