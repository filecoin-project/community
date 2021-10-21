## Project Name

Defi Together

## Category

Application

## Project Description

Defi Together allows groups of friends to invest in Defi and share the returns with no trust required. The project allows users to start a group, add friends and propose defi transactions. Group members deposit their funds into Gnosis Safe, a multi-signature ETH wallet, and the safe can make defi transactions on behalf of the group.

To faciliate making Defi investment decisions amongst the group members, there needs to be tools for them to communicate. E.g., investment idea proposals and feedback, polls, chats, etc. All these interactions will need to store their states in a storage layer. In addition, access to these tools and their states should only be given to the group members.

As an example, currently online conversations between Gnosis Safe members are done offchain in some centralized platform (e.g. Telegram, Discord, etc) where the chatrooms have no onchain relationship with the wallets and their signatories. Access and membership to the wallets and to the chatrooms are managed separately, which can result in the two systems to be out of sync. Furthermore, the centralized chatroom services are subject to interruption or shutdown, something that isn't as much of a problem for decentralized wallets.

Given a decentralized storage layer that is tied to a Gnosis Safe, we intend to build a commenting app (a simplified Disqus) that allows Gnosis Safe members to discuss defi investing ideas right in the Gnosis Safe interface. As all the code and comments are stored through Ceramic to IPFS, it is not subject to the problems of centralized chatroom platform mentioned earlier. As a next step, more structured group interaction mechanisms such as polls can be added to the decentralized storage where onchain transactions can be triggerd by these interactions (e.g. an investment into a yield farm is triggered automatically if a poll concludes as such).

In order to provide the safe app and the safe owners with authorized access to decentralized storage, we will use Ceramic and implement the Safe DID Method [CIP-101](https://github.com/ceramicnetwork/CIP/blob/main/CIPs/CIP-101/CIP-101.md).

To speed up development time, the initial implementation will be a Gnosis Safe App. A separate web app can be built at a later stage.

## Project Status

Under Development

## Previews

![Starting a new defi investing group](https://user-images.githubusercontent.com/46126470/138233589-caf51278-723d-416b-896b-a97c61f4b726.jpg)
![Setting the starting capital](https://user-images.githubusercontent.com/46126470/138233596-a1b47fa6-914e-4375-adee-82515ff685aa.jpg)
![Proposing a defi investing transaction](https://user-images.githubusercontent.com/46126470/138233605-9c11799d-d44e-42c3-ae2f-f51ccdad4fee.jpg)

## Target Audience

People who are interested in Defi. Experienced users are expected to setup the initial group & safe, while inexperienced users are expected to be invited and guided by the experienced users.

## Rough estimated user base (if applicable)

We will open it to our community as soon as this project turns to beta.

## Github repo

[Defi Together](https://github.com/flyingnobita/defi-together)

[Gnosis Safe DID Resolver](https://github.com/flyingnobita/safe-did-resolver)

## Website

[ETHGlobal HackFS 2021 Showcase](https://showcase.ethglobal.com/hackfs2021/defi-together-moon-together)

## Docs

N/A

## Team Info

- Flying Nobita - Web3 developer

- Graeme - Product manager @GnosisSafe

### Team Size

2

### Team members

- Flying Nobita
- Graeme

## How the community can engage

GitHub Discussion: [https://github.com/filecoin-project/community/discussions/335](https://github.com/filecoin-project/community/discussions/335)  
Email:  
Slack:  
Twitter:  
Discord:  
Telegram:  
WeChat:

## How to Contribute

As we are still early in the development phase, we are interested in hearing use cases and ideas for our project. We also welcome any coders that are interested in contributing in whatever way possible.
