## Project Name <!-- Add your project name here with format "Project Name"-->
FILterBot
## Category 
<!--developer tooling, application, wallet, infrastructure, etc-->
Infrastructure
## Project Description
<!--Describe your project in a few sentences. -->
Filecoin Foundation needs a bot that can periodically check specific GitHub repos, tally issues, and post a message in certain Slack channels. We will utilize this bot across multiple workstreams, so it needs to be configurable for different teams.

**Current workstreams/teams:** FIPs/Community Governance, Filecoin Plus notaries, Filecoin Plus large datasets
### Example workstream:
Every Wednesday, bot will check Filecoin Plus Client Onboarding repo (https://github.com/filecoin-project/filecoin-plus-client-onboarding) and tally issues that are Open and labeled: `bot:LookingGood` & `state:Verifying`. Bot will then post a comment in the Filecoin community slack channels `#fil-plus` and `#fil-plus-notaries`. 

Sample message, simple version:
> There are 35 open client applications for DataCap that can be reviewed and verified! You can find those open issues [here](https://github.com/filecoin-project/filecoin-plus-client-onboarding/issues?q=is%3Aopen+label%3Abot%3AlookingGood+label%3Astate%3AVerifying).


Could expand to include additional metrics or details, such as X number of applications have been granted in the past week. 
## Project Status
<!--brainstorming, fundraising, under development, beta, shipped, etc-->
Under development
## Previews
<!--Add some screenshots to give a preview of your product-->
none yet
## Target Audience
<!--Describe who will be your project's users-->
Filecoin Foundation to manage, but will engage with Filecoin community slack as well. These reminder notifications could be useful to notaries and others engaged in community governance. 
## Rough estimated user base (if applicable)
<!--How many users do you have right now?-->
There are currently ~30 notaries in Filecoin Plus. The number of engaged community members following FIPs is much larger.
## Github repo
<!--Attach a link to your GitHub repo if it's OSS-->
Will update to include
## Website
<!--Link your website if available-->

## Docs
<!--Including a link to your project docs!-->

## Team Info
<!-- Introduce your amazing team - how many team members are working on this project and who are they?-->
### Team Size  
1, with advisors from Filecoin Foundation
### Team members  
Jeremy Rose: https://github.com/nornagon

## How the community can engage
GitHub Discussion: https://github.com/filecoin-project/community/discussions/270

Slack:  @Galen McAndrew 

## How to Contribute
<!--How can the community contribute to your project?-->
Would be interested in hearing how others may want to utilize this kind of reminder bot, or future features that would be useful. Most GitHub <> Slack bot integrations are designed around teams and push triggers (such as a new PR being created), but the goal here is to create some reminders and potential analytics that showcase (and encourage) community engagement.
