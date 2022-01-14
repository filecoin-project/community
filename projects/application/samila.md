## Project Name <!-- Add your project name here with format "Project Name"-->
Samila
## Category 
<!--developer tooling, application, wallet, infrastructure, etc-->
Application
## Project Description
<!--Describe your project in a few sentences. -->
**Samila** is a user-friendly and easy-to-use generative art generator library written in Python, **Samila** lets you create arts based on many thousand points. The position of every single point is calculated by a formula, which has random parameters. Because of the random numbers, every image looks different.
**Samila** is integrated with **NFT.Storage** and has this option to upload generated arts directly.
## Project Status
<!--brainstorming, fundraising, under development, beta, shipped, etc-->
Beta
## Previews
<!--Add some screenshots to give a preview of your product-->
```pycon
>>> import matplotlib.pyplot as plt
>>> from samila import GenerativeImage
>>> g = GenerativeImage()
>>> g.generate()
>>> g.plot()
>>> plt.show()
```
![1](https://raw.githubusercontent.com/sepandhaghighi/samila/master/otherfiles/images/7.png)

```pycon
>>> import random
>>> import math
>>> def f1(x,y):
    result = random.uniform(-1,1) * x**2  - math.sin(y**2) + abs(y-x)
    return result
>>> def f2(x,y):
    result = random.uniform(-1,1) * y**3 - math.cos(x**2) + 2*x
    return result
>>> g = GenerativeImage(f1,f2)
>>> g.generate()
>>> g.plot()
>>> g.seed
188781
>>> plt.show()
```
![2](https://raw.githubusercontent.com/sepandhaghighi/samila/master/otherfiles/images/1.png)

```pycon
>>> from samila import Projection
>>> g = GenerativeImage(f1,f2)
>>> g.generate()
>>> g.plot(projection=Projection.POLAR)
>>> g.seed
829730
>>> plt.show()
```
![3](https://raw.githubusercontent.com/sepandhaghighi/samila/master/otherfiles/images/2.png)

## Target Audience
<!--Describe who will be your project's users-->
Generative art lovers and anyone that wants to venture into the world of NFTs
## Rough estimated user base (if applicable)
<!--How many users do you have right now?-->
1000 - 5000
## Github repo
<!--Attach a link to your GitHub repo if it's OSS-->
https://github.com/sepandhaghighi/samila
## Docs
<!--Including a link to your project docs!-->
https://github.com/sepandhaghighi/samila#usage
## Team Info
<!-- Introduce your amazing team - how many team members are working on this project and who are they?-->

### Team Size  
2
### Team members  
- [Sepand Haghighi](https://github.com/sepandhaghighi) - Core Developer
- [Sadra Sabouri](https://github.com/sadrasabouri) - Core Developer
## How the community can engage
GitHub Discussion: https://github.com/filecoin-project/community/discussions/446

Email: sepand.haghighi@yahoo.com

Twitter: https://twitter.com/samila_arts

Discord: https://discord.com/invite/94bz5QGZWb
	           				
Telegram:  https://t.me/samila_arts

Instagram: https://www.instagram.com/samila_arts

## How to Contribute
<!--How can the community contribute to your project?-->
- Create issues in https://github.com/sepandhaghighi/samila/issues
- Submit pull requests on here https://github.com/sepandhaghighi/samila [Samila Contribution Guideline](https://github.com/sepandhaghighi/samila/blob/master/.github/CONTRIBUTING.md)
- Join our communities
