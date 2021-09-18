## Project Name MyWorld<!-- Add your project name here with format "Project Name"-->

## Category 
<!--developer tooling, application, wallet, infrastructure, etc-->
Application

## Project Description
<!--Describe your project in a few sentences. -->
MyWorld is a common place for autism artists to express their world through arts and music. They can sell and exchange their work via the smart contracts. A small fee from those buying and selling is contributed to autism awareness activies; those activities in turn are proposed and voted by mean of token distribution in the community.
All those beautiful things happend thanks to the greatness of Flow blockchain network, NFT.storage API and IPFS storage space.

## Project Status
<!--brainstorming, fundraising, under development, beta, shipped, etc-->
We are in beta with a functional product running on Flow testnet.

## Previews
<!--Add some screenshots to give a preview of your product-->
1. Welcome Screen
    ![Screen 1](https://mywnft.github.io/shot/sign-in.png)

2. Home Screen
    ![Screen 2](https://mywnft.github.io/shot/home.png)    

3. Upload Image to IPFS
    ![Screen 3](https://mywnft.github.io/shot/upload-mint.png)

4. Mint NFT
    ![Screen 4](https://mywnft.github.io/shot/success.png)

4. NFT Gallery
    ![Screen 5](https://mywnft.github.io/shot/gallery.png)

## Target Audience
<!--Describe who will be your project's users-->
Autism Artists
Autism Musicians

## Rough estimated user base (if applicable)
<!--How many users do you have right now?-->
We are opening to our community soon

## Github repo
<!--Attach a link to your GitHub repo if it's OSS-->
https://github.com/NguyenIvan/lazy-ipfs-image
https://github.com/NguyenIvan/MyWorld/

## Website
<!--Link your website if available-->
https://mywnft.github.io

## Docs
<!--Including a link to your project docs!-->

## Team Info
<!-- Introduce your amazing team - how many team members are working on this project and who are they?-->
nwin lee
I train kids in various disciplines, especially martial arts and sport climbing. I am also a coder.

Lynda P.
I work with autistic children to improve their cognitive behaviour and physical wellness. In my free time I have fun with my crypto tokens.

### Team Size  
2

### Team members  
nwin lee
a.mac@qhoach.com

Lynda P. 
na.le@qhoach.com

## How the community can engage
GitHub Discussion: https://github.com/filecoin-project/community/discussions/307 <!--Start a disucssion with the community here: https://github.com/filecoin-project/community/discussions/new and attach the link!-->  
Email: a.mac@qhoach.com
Slack:  
Twitter:  
Discord:  https://discord.gg/nujAyCAdv9
Telegram:  
WeChat:  

## How to Contribute
<!--How can the community contribute to your project?-->
There are lots of things to improve in my component [lazy-ipfs-image](https://github.com/NguyenIvan/lazy-ipfs-image). I created this component because if we upload an image to IPFS (through NFT.storage api) and <em>wait</em> for it to render, it would takes several minutes to be available (depends how busy the servers are, I guess). That long wait can cause panic in users and break browser rendering. 
My solution to that problem is to lazy load the image and use [fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch) function to wait after the upload is done, so that the http request will not be timed out. In the waiting time a placeholder is displayed in place of the image.
I would add several features to the component:
- Save IPFS link to the user storage space, so incase the ipfs is not available in time, it can be displayed when the user comes back.
- Also upload to S3 so that the user can see it even if it is not readily available from IPFS.