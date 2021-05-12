# Community

- [Community](#community)
  - [About](#about)
  - [Join the Community](#join-the-community)
    - [Forums](#forums)
      - [Filecoin Community Forum](#filecoin-community-forum)
      - [lotus Discussion Forum](#lotus-discussion-forum)
      - [Filecoin Proving Subsystem Discussion](#filecoin-proving-subsystem-discussion)
    - [Implementation Related Repo](#implementation-related-repo)
    - [Chat](#chat)
    - [GitHub issues](#github-issues)
    - [Security issues and disclosures](#security-issues-and-disclosures)
  - [Useful links](#useful-links)
  - [Ecosystem Projects](#ecosystem-projects)
    - [Showcase Your Project!](#showcase-your-project)
    - [Updates and Newsletter](#updates-and-newsletter)
    - [Filecoin Shipyard](#filecoin-shipyard)
  - [Events](#events)
    - [Community calls](#community-calls)
    - [Filecoin Meetups](#filecoin-meetups)
  - [Contributing](#contributing)
    - [Contributing Guidelines](#contributing-guidelines)
  - [Maintainers](#maintainers)
  - [License](#license)

## About

Welcome to the Filecoin community repository! You can treat this repo as your go-to for all meta, non-code discussions in the [*Discussions Forum*](https://github.com/filecoin-project/community/discussions), documents used by multiple repositories (such as the Code of Conduct), and how to interact with the Filecoin project and other community members.

To get the latest network notifications, subscribe to [status.filecoin.io](https://status.filecoin.io).

If you are interested in discussing code or protocol design, feel free to come talk to us on our [forums](#forums), [chat channels](#chat), or in issues on our other [Filecoin project repos](https://github.com/filecoin-project).

## Join the Community

**> Note: Before posting to different communications channels, make sure to read the [Code of Conduct](https://github.com/filecoin-project/community/blob/master/CODE_OF_CONDUCT.md).**

The vast majority of the Filecoin Project conversations, including implementation, community support, ecosystem news, etc. take place on:

- [Forums](#forums) (mainly on Github Discussions)
- GitHub Issues (see [Implementation related repo](#impelmentation-related-repo) section below)
- Chat (mainly on Slack) (see [Chat](#chat) section below)

The Filecoin Project is an open sourced project with a very supportive and welcoming community, where many community members are responsive in various of forums and slack channels. We also have [Filecoin community ambassadors](https://github.com/filecoin-project/community/discussions/116#discussioncomment-617066) here to support you, tag their GitHub handlers in GitHub discussions or @fil-community-ambassadors in all slack channels if you have any questions!

Implementation dev teams tend to check their corresponding GitHub repo issues and discussions regularly and try to respond within 5 business days.

We also push updates to the community via:

- Forum - [`Network and implementations updates`](https://github.com/filecoin-project/community/discussions/categories/network-and-implementations-updates) updates and [`news and events`](https://github.com/filecoin-project/community/discussions/categories/news-and-events)
- Filecoin blog: [https://blog.filecoin.io](https://blog.filecoin.io)
- CryptoComputeLab blog(proof updates): [https://research.protocol.ai/groups/cryptocomputelab/](https://research.protocol.ai/groups/cryptocomputelab/)
- Youtube: [Filecoin](https://www.youtube.com/channel/UCPyYmtJYQwxM-EUyRUTp5DA)
- Twitter: [@Filecoin](https://twitter.com/Filecoin)
- WeChat ID: Filecoin-Official

![filecoin qr code](/images/qrcode_for_gh_da36751a6108_1280.jpg)


### Forums

#### Filecoin Community Forum

When in doubt or curiosity, please post in [Filecoin community forum](https://github.com/filecoin-project/community/discussions)!

We love to hear what the community has to say, whether it is to:

- Ask a question
- Gather community feedback on a new feature proposal before opening an FIP 
- Share a new project you're working on
- Find collaborators for your own community project
- And whatever else! Honestly!

The discussion forum uses the same Code of Conduct as our other community channels. Please make sure to read this before posting.

> Note: A Chinese-language community forum is also available at https://github.com/filecoin-project/community-china/discussions. It is managed by [CoinSummer](https://github.com/CoinSummer).

#### lotus Discussion Forum

[lotus discussion](https://github.com/filecoin-project/lotus/discussions) is an all-in-one place where you can track [lotus releases and announcements](https://github.com/filecoin-project/lotus/discussions/categories/announcement), find [tutorials](https://github.com/filecoin-project/lotus/discussions/categories/tutorials) ask questions about running[ a lotus node](https://github.com/filecoin-project/lotus/discussions/categories/syncing), [lotus miner ](https://github.com/filecoin-project/lotus/discussions/categories/miner-q-a)or lotus client, get help with troubleshooting, [share your lotus setup or thoughts](https://github.com/filecoin-project/lotus/discussions/categories/show-and-tell), chat with your fellow developers with [how to build ](https://github.com/filecoin-project/lotus/discussions/categories/developer-q-a)applications using lotus JsonRPC API and so on.


#### Filecoin Proving Subsystem Discussion

The Filecoin Proving Subsystem (or FPS) provides the storage proofs required by the Filecoin protocol. If you have any question regard to the current proof, feedbacks for proof performance on different machines, ideas to improve proof or implementing new proof, join the [forum here](https://github.com/filecoin-project/rust-fil-proofs/discussions)!

### Implementation Related Repo

### Chat

Vast majority of community live chat is happening in [Filecoin Project Slack](https://filecoin.io/slack). Tag @fil-community-ambassadors if you have any questions!

Fun channels to join once you are in the workspace:

- `#fil-announcements`: This channel is for official Filecoin announcements only (including network, implementations, and ecosystem announcements). Join to get most up-to-date news. Please do not post questions or other messages here; they will be deleted! 
- `_fil-lobby`: for general Filecoin-related sharing
- `fil-help`: ask questions here if you can't find another specific channel for your question
- `fil-lotus`: for lotus related discussion
- `fil-fips`: for [Filecoin Improvement Proposals](https://github.com/filecoin-project/FIPs) related discussion 
- `fil-plus`: for Filecoin Plus([notary-governance](https://github.com/filecoin-project/notary-governance)) related discussion
- `fil-net-calibration-discuss`/`fil-net-nerpa-discuss`: for testnet disucssions
- `fil-ecosystem-dev`: for updates and discussion about building in the Filecoin ecosystem
- `fil-deal-market`: promote your miner as a storage provider or find your provider as a client here
- `hackathons-help`: join this channel if you are participating any Filecoin hackathons and have questions

Primary Slack channels are bridged (automatically mirrored and read-only) to [Matrix](https://app.element.io/#/group/+filecoin:matrix.org).


### GitHub issues

If you find something puzzling or encounter a straight-up bug in any of our repositories, please file a well-scoped issue. The issue lists for our most active repositories are below:

- [`lotus`](https://github.com/filecoin-project/lotus/issues) ([contribution guide](https://github.com/filecoin-project/lotus#contribute))
- [`venus`](https://github.com/filecoin-project/venus/issues)
- [`specs-actors`](https://github.com/filecoin-project/specs-actors/issues)
- [`rust-ffi-proofs`](https://github.com/filecoin-project/rust-fil-proofs)
- [`specs`](https://github.com/filecoin-project/specs/issues)

If a repo has a Contributing Guide, please read it before filing an issue!

### Security issues and disclosures

Almost anything you find that is a bug in the codebase should be filed as an issue. The exception is if you find a security vulnerability. The Filecoin protocol is still under heavy development. This means that there may be problems in our protocol design or implementations. Though Filecoin is not yet production-ready, many people are already running nodes on their machines. So we take security vulnerabilities very seriously! If you discover a security issue, please bring it to our attention right away!

Please refer to [SECURITY.md](./SECURITY.md) document found in this repo on how to best report findings and participate on the bug bounty program.

## Useful links

If you are new to the Filecoin Project, below are some helpful links for you to learn more about it:
- Official website: [https://filecoin.io](https://filecoin.io)  
- [Filecoin Specification](https://spec.filecoin.io): contains documents, code, models, and diagrams that constitute the specification of the Filecoin Protocol.
- [Filecoin Docs](https://docs.filecoin.io): offers all the necessary resources to learn about Filecoin, the software and the tools to contribute to the network, either as a user looking for storage, or as a miner providing it  

## Ecosystem Projects

If your project uses Filecoin, you're in the Filecoin ecosystem! We'd love to see all awesome projects that are built on top of the Filecoin ecosystem to be known and get used by the Filecoin community! 

### Showcase Your Project!

Following the steps below to submit your projects to be featured in this [repo](https://github.com/filecoin-project/community/tree/master/projects):
- Create a project profile using the [project submission template](https://github.com/filecoin-project/community/blob/master/templates/project-submission-template.md). Name the file name after your project and fill in as much information as you can.  Use your project name as the file name so the community can find your project easily!
- Create a project discussion, with the category as Show and tell - Developers  and title as `[Category] Project Name`(i.e: `[Application] Slate`), link the discussion in the How the community can engage section. This is to create a place to interact with the Filecoin community, share your updates and gain feedback on your projects!
- Once the project profile is ready, create a [PR](https://github.com/filecoin-project/community/pulls), prefix `[Project Submission]` in the title, and request a review from one of the [maintainers](#maintainers).
- Let the maintainer know if you want your [updates](#updates-and-newsletter) to be featured in [Filecoin newsletter](https://mailchi.mp/filecoin.io/subscribe) or not in the PR description!
- If everything looks good, the maintainer will merge the pr and voila, as simple as that your project is now featured here!

### Updates and Newsletter

We'd encourage all projects featured in this repo to share all of your thrilling updates with the community! Start a new comment with header `Project Name Update/Newsletter - Date` (i.e `## Slate Update - Feb, 2021`) in your project discussion to share the exciting news with the community!

### Filecoin Shipyard

[Filecoin Shipyard](https://github.com/filecoin-shipyard) is a home we created for projects built by the Filecoin community. We encourage you to take a look around to explore some early projects incubated by the Filecoin community! If you're building something new on top of Filecoin, feel free to request to to add your project to the Shipyard!


## Events

Add our [Google Calendar](https://calendar.google.com/calendar/b/6?cid=ZmlsZWNvaW4ub3JnX2o3bW1ldjI0ZzgwcmVsbzU2cHFtMWVsMWUwQGdyb3VwLmNhbGVuZGFyLmdvb2dsZS5jb20) or follow issues in this repo to keep track of events (meetups, hackathons, etc.) hosted by the Filecoin Project and/or Protocol Labs.

### Community calls

Our community calls are venues for all Filecoin Project community members to meet each other, share demos of recent work, discuss open problems, and more. We expect these calls to be extremely respectful venues where all community members follow our [Code of Conduct](https://github.com/filecoin-project/community/blob/master/CODE_OF_CONDUCT.md) and treat each other (i) as they would like to be treated and (ii) as they would treat each other in real life.

All community calls are **open for anyone to join**. However, we recommend that you take a look at each call's agenda (which can be found on GitHub issues under the label [`agenda`](https://github.com/filecoin-project/community/labels/agenda)) to make sure the call will be a good use of your time. We do our best to group similar demos and other agenda items together in the same call so it is easier to choose calls that you would like to attend.

Furthermore, we hold different calls for different communities. If you are a third-party app developer or OSS contributor, you might be interested in attending our **monthly development community calls** that are geared towards topics that developers will find useful. We also hold occasional **mining community calls** that are geared towards the needs of Filecoin miners.

Feel free to attend whichever calls are interesting to you. All calls are recorded, and the recording will be posted online at this repo.

Learn more about:

- [Development Community Calls](https://github.com/filecoin-project/community/blob/master/community-calls/dev-calls/dev-calls.md)
- [Mining Community Calls](https://github.com/filecoin-project/community/blob/master/community-calls/mining-calls/mining-calls.md)

We will announce each upcoming community call by making announcements in our [chat channels](#chat) and [website](https://filecoin.io/build/#events).

### Filecoin Meetups

Filecoin meetups are a great way to meet and connect with other developers and miners in your community that are using and learning about Filecoin.

Click [Attend a Filecoin virtual meetup](https://www.meetup.com/Filecoin-San-Francisco/events/276433326/) for joining the next event!


## Contributing

### Contributing Guidelines

We use a common [Code of Conduct](https://github.com/filecoin-project/community/blob/master/CODE_OF_CONDUCT.md) across all of our repos.

Each repo should have its own contributing guide, called `CONTRIBUTING.md`. Here is an example [Contributing Guide for `venus`](https://github.com/filecoin-project/venus/blob/master/CONTRIBUTING.md).

## Maintainers

Maintainers are responsible for maintaining the content of this repo, create an issue and tag one of the maintainers if you have any questions.

Current maintainers are:
@jennijuju ([jennijuju@protocol.ai](jennijuju@protocol.ai))


## License

The Filecoin Project is dual-licensed under Apache 2.0 and MIT terms:

- Apache License, Version 2.0, ([LICENSE-APACHE](https://github.com/filecoin-project/community/blob/master/LICENSE-APACHE) or [http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0))
- MIT license ([LICENSE-MIT](https://github.com/filecoin-project/community/blob/master/LICENSE-MIT) or [http://opensource.org/licenses/MIT](http://opensource.org/licenses/MIT))
