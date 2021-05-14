---
title: "Vitess Arewefastyet"
summary: intergrating benchmarks for the open source repository vitess
date: 2021-05-14
tags: ["vitess","benchmark"]
author: "Akilan Selvacoumar"
draft: false
aliases: [/arewefastyet]
weight: 2
---
## Introduction 
The purpose of this project is to do a benchmark run when ever there is a push. The background activity is fairly simple, we create our own bare metal server. Once this server is created we run a bunch of ansibles(for sysbench) and once the run is complete we read the results and store them in a mysql instance. Once the following operations are complete we take down the server. 

#### Project Link: https://github.com/vitessio/arewefastyet
#### website link: https://benchmark.vitess.io

## Objectives 
1. Creates a VPS
2. Runs the ansibles on the VPS
3. Reads benchmark results 
4. Kills VPS 

## Architecture 
![](https://raw.githubusercontent.com/vitessio/arewefastyet/master/docs/architecture/arewefastyet_architecture.png)

## SQL Schema
![](https://raw.githubusercontent.com/vitessio/arewefastyet/master/docs/architecture/sql/arewefastyet_schema.png)

