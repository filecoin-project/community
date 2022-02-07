## Project Name 

sched-plugin

## Category 

application

## Project Description

At present, the lotus sector [sched](https://github.com/filecoin-project/lotus/blob/master/extern/sector-storage/sched.go) module pays more attention to versatility. It is undoubtedly more general. However, in the actual sealing process, miners may have different needs, and it is likely that lotus `sched` needs to be customized, such as AP/P1 /P2 binding to prevent files transfer, limit the number of workers running, etc. all of which require miners to have technical reserves. 

An effective and flexible scheduling system that can greatly contribute to sealing efficiency. This project is implementing a goal: change the `sched` module of lotus to a `sched-plugin`.

It will bring the following benefits:

- Increase community activity, community members can develop `sched-plugin` according to the actual situation, and this `sched-plugin` is also likely to be used by others.
- For different scenarios, different`sched-plugin` can be used to increase sealing efficiency and cluster scale.

## Project Status

fundraising/udender development

## Previews

- change the `sched` module of lotus to a `sched-plugin`. lotus `sched` can use multiple `plugins`.
- develop a `default plugin` based on the `sched` module of lotus.
- develop a custom plugin to support custom functions such as task binding/running limit.
- maintain `sched-plugin` branch until mature, try to merge into lotus master.

## Target Audience

miner

## Rough estimated user base (if applicable)

N/A

## Github repo

https://github.com/llifezou

## Website

N/A

## Docs

https://github.com/llifezou

## Team Info

A small team.

### Team Size  

1

### Team members  

llifezou

## How the community can engage

GitHub Discussion: https://github.com/filecoin-project/community/discussions/463
Email:  llifezou@gmail.com

## How to Contribute

N/A