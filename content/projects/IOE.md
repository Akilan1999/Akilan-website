---
title: "Internet Of Energy"
summary: Prototype Implementation of energy transcations in a micro grid. 
tags: ["Internet Of Energy","Decentralized","Micro Grids","Transactional","battery"]
author: "Akilan Selvacoumar"
draft: false
aliases: [/IOE]
weight: 4
---

## Introduction 
![](http://www.networkrevolution.co.uk/wp-content/uploads/2014/04/img-smartgrid-problem.png)
This  project  aims  to create  a  marketplace  where  anyone generating  energy  by  using  renewable  sources  can  sell  it  to anyone in the grid. This will in most cases will be cheaper and aims  to  have  no  carbon  emissions.This  entire  platform  has two  versions,  a  centralized and  a decentralized  version.The centralized  version uses  the  client-server  architecture while decentralized  version  uses  the  concept  of  a  transactional battery along with relay modules which is used to forward and receive  power  from  other  batteries. We  were  able  to  transfer energy from one power bank to the other using relays. 

#### website: https://ioe.hwtech.club
#### Github organization page: https://github.com/internet-of-energy/
#### White Paper: https://ioe.hwtech.club/pdf/white_paper_v3.pdf

## Main repositories
1. [Centralized IOE](https://github.com/internet-of-energy/Centralized_IOE): We will use a simple backend model that can communicate with smart meters at home to control the flow of the electricity. The client-server architecture has a lot of support and tools available for development. This means we can create functioning platform with a lot of features at a quicker pace.
2. [IOE relays api](https://github.com/internet-of-energy/IOE_relays_api): The Concept of IOE is that anyone can buy electricity from anyone. Once a transaction is successful there must be a way to transfer electricity. This code will run on a raspberry pi and using relays it will control the flow of electricity.
3. [IOE electricity cost](https://github.com/internet-of-energy/IOE-electricity-cost): In this repo we will focus on designing a module that helps decide the cost in the electric grid based on supply and demand. 





