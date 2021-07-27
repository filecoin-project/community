
## Project Name <!-- Add your project name here"-->
box

## Category 
developer tooling

## Project Description
<!--Describe your project in a few sentences. -->
The mainstream developer experience in the world of independent front-end developers is to purchase a managed service provided by a cloud vendor, which abstracts away the complexity of dealing with back-end development and enable front-end developers to focus on end-to-end user experience for their clients. Currently, there is no option for a front-end developer to build on top of IPFS with a "Developer Experience" similar to serverless functions. They need to run a full js-ipfs node on the platform they want to develop on, for example on Android, which has different file system access than iOS or other operating systems. "box" is an IPFS node which aims to separate the server from front-end development and provides front-end APIs for developers to connect to, using Libp2p, giving them the same experience as a cloud server for any "box" node. To give a full application server experience to the developer, two protocols are being developed in "box" for a start:
* File Protocol
* Data Protocol

Front-end developers work with a "box" like a server without the need to run a full IPFS node on the platform they develop for, and interface with the "box" node to store or fetch data using libp2p. End users, their clients, can treat "box" like a server to keeps their data safe and gives them all functionalities of IPFS like cluster synchronization. If they lose their phone with the application installed, their files are safe in the "box" node.

## Project Status
<!--brainstorming, fundraising, under development, beta, shipped, etc-->
We have completed the initial brainstorming and design phases, and currently completing development phase for the first prototype. Our first application is a [Google Photos Alternative](https://github.com/funcitonland/photos) which connects to the "box", and demo is ready. Currently, we are working on building [a library on top of libp2p](https://github.com/functionland/box) for upload/download of photos from the app to/from the "box".

## Previews
<!--Add some screenshots to give a preview of your product-->
![https://dev.to/fx/google-photos-open-source-alternative-with-react-native-80c](https://raw.githubusercontent.com/functionland/functionland.github.io/main/static/images/box-diagram.jpg)

Below is a GIF demo from "Photos" application, which is a react native app, as the first demo of how an application interacts with "box"

![https://dev.to/fx/google-photos-open-source-alternative-with-react-native-80c](https://raw.githubusercontent.com/functionland/blog/main/photos-intro-dev-to/photos.gif)

## Target Audience
<!--Describe who will be your project's users-->
Our primary target audience is the average front-end developers who are hands-on with managed cloud service platforms. "box" gives them the ability to develop applications on top of IPFS. Using the “graph” library, they interface with IPFS backend, through an API format that they have prior experience in.
The secondary target audience is the application users who are looking for a decentralized and privay-centered alternative of paid services, such as Google Photos. They are able to turn any hardware into a back-end, and while enjoying the privacy of a private node, have the safety of cloud storage, with Filecoin and data synchronization. Thanks to Libp2p and IPFS, no static IP or domain is needed to access their “box” data from anywhere in the world.

## Rough estimated user base (if applicable)
<!--How many users do you have right now?-->
Considering Google Photos has 2B users and in most surveys at least 20% want to switch to an alternative solution after free tier being removed, there is a huge 250M potential users.
The project is not live yet but our github page received around 400 stars and we have some subscribers to our newsletter.

## Github repo
<!--Attach a link to your GitHub repo if it's OSS-->
[For Photos application as the first box app](https://github.com/functionland/photos/)

[For box backend, which stores the data nad provides front-end API library to talk to box](https://github.com/functionland/box)

## Website
<!--Link your website if available-->
[Main website](https://fx.land)

[An article about box](https://dev.to/fx/google-photos-open-source-alternative-with-react-native-80c)

## Docs
<!--Including a link to your project docs!-->
https://github.com/functionland/photos/blob/main/README.md

## Team Info
<!-- Introduce your amazing team - how many team members are working on this project and who are they?-->
### Team Size  
4

### Team members  
**Keyvan** is an avid open-source contributor since 2012 (when he joined OpenCog's AGI development team). He holds an MSc in Artificial Intelligence from University of Southampton, UK. He's served in various technical executive positions for about a decade and been affiliated with many start-ups, including two that he co-founded.

* [Github Page Link](https://github.com/keyvan-m-sadeghi)
* [LinkedIn Page Link](https://www.linkedin.com/in/keyvanmsadeghi/)


**Kate** is a business development and commercialization specialist and has worked with multiple startups and SMEs to realize their non-dilutive funding, investment, and revenue generation goals. Strategic project advisor to Centennial College's projects involving machine learning. Bootstrapping a B2B marketplace technology startup in the construction sector. PhD in Plant Agriculture, Ontario Agricultural College, Msc. from Michigan State University in Crop and Soil Science with focus on statistical analysis. 
* [Github Page Link](https://github.com/kitty2121)
* [LinkedIn Page Link](https://www.linkedin.com/in/kate-withers-hess-phd-33530023/)


And we have two more team members with the same first name, so we added the last name too :)

**Ehsan Emami** is a senior hardware development lead, currently working at Amazon and previously at Apple and Gopro. With 12 years of hardware/software architecture experience, he has been a key contributer in defining, developing and fine-tuning many mass market products. Ehsan obtained his master's degree from University of Waterloo in Electrical Engineering.
* [Github Page Link](https://github.com/ehsan-git-dev)
* [LinkedIn Page Link](https://www.linkedin.com/in/ehsan-emami-0005bb6/)


**Ehsan Shariati** studied electrical engineering and got his master's degree from University of Colorado at Boulder. He is a full stack developer with over 10 years of professional application development, who is experienced in Javascript frameworks, such as Angular, AngularJS, React and React Native, as well as PHP, C, C++, C#, JAVA, Python, MySQL, MSSQL, Linux. He is also a project manager, and has PMP, ITIL and SCRUM certificates. He has developed a shopping mall ERP system for the largest shopping mall in Iran(Isfahan City Center), as well as an insurance ERP for Dana insurance in Iran.
* [Github Page Link](https://github.com/ehsan6sha)
* [LinkedIn Page Link](https://www.linkedin.com/in/ehsanehsan/)

## How the community can engage
GitHub Discussion: https://github.com/filecoin-project/community/discussions/217
Email:  info@fx.land
Slack:  
Twitter:  https://twitter.com/functionland
Discord:  https://discord.gg/ebaVDnfp
Telegram:  https://t.me/functionland
WeChat:  

## How to Contribute
<!--How can the community contribute to your project?--> 
We appreciate contributions on any level, code, docs, discussions, anything! A good place to start is issues labeled as "Good first issue" over at GitHub.
