## Project Name 

Miner-tools

## Category 

application

## Project Description

The `filecoin toolbox` to facilitate miners to better participate in filecoin.

The purpose of improving this `toolbox` is to minimize the loss of miners in emergencies and to facilitate the deployment of wdpost certification services for miners.

1.Redo program with scheduling

- When all sectors or some sectors are accidentally damaged, the sectors need to be quickly restored to avoid punishment. The `lotus-redo` tool in `lotus-box` is suitable for a small amount of sector recovery. so a service is needed to support the redo sector of multiple machines.
- Provided functions: 
  - compatible with `lotus-worker`
  - supports the rerun of sectors based on deadline and partition, and supports the rerun of custom sectors


2.wdpost server

- Lost the metadata of the miner, Only the private key, but the sector file still exists, quickly start a wdpost service.
- Provided functions: 
  - simple configuration, quick start.
  - support for multiple miners to provide wdpost proof, easy to manage multiple miners.

## Project Status

fundraising/udender development

## Previews

1.Redo program with scheduling

- Multi-machine redo sectors.

2.wdpost server

- Simple to quickly start the wdpost service that supports multiple miners

## Target Audience

all miner

## Rough estimated user base (if applicable)

N/A

## Github repo

https://github.com/luluup777

## Website

N/A

## Docs

https://github.com/luluup777

## Team Info

A small team.

### Team Size  

1

### Team members  

luluup777

## How the community can engage

GitHub Discussion: https://github.com/filecoin-project/community/discussions/352  
Email:  luluup777@163.com

## How to Contribute

If you want, act now