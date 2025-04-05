---
title: "Patch: Using remote ScreenShare ,keyboard and mouse using laplace and Barrier"
summary: Modifying the open source project laplace to allow remote keyboard and mouse during screenshare
date: 2021-07-05
aliases: ["/laplace-keyboard-mouse"]
tags: ["WebRTC","laplace"]
author: "Akilan Selvacoumar"
draft: false 
aliases: [/laplace-keyboard-mouse]
weight: 2
---

## What is laplace ?
" Laplace is an open-source project to enable screen sharing directly via browser. Made possible using WebRTC for low latency peer-to-peer connections, and WebSocket implemented in golang for WebRTC signaling. "

link: https://github.com/adamyordan/laplace

Link to my branch which has Barrier intergrated with Barrier KVM:
https://github.com/Akilan1999/laplace/tree/keyboard_mouse

Link to the pull request: https://github.com/adamyordan/laplace/pull/8


## Installation


### Installation required to share keyboard and mouse
To do this we ensure that the client either has has a IPV6 
address or a public IPV4 address. 
We use the use the popular open repository known as [Barrier KVM](https://github.com/debauchee/barrier). 

#### What is Barrier kvm?

"Barrier is software that mimics the functionality of a KVM switch, which historically would allow you to use a single keyboard and mouse to control multiple computers by physically turning a dial on the box to switch the machine you're controlling at any given moment. Barrier does this in software, allowing you to tell it which machine to control by moving your mouse to the edge of the screen, or by using a keypress to switch focus to a different system." [Barrier KVM](https://github.com/debauchee/barrier)

#### Barrier KVM build status and links to install 
|Platform       |Build Status|
|            --:|:--         |
|Linux          |[![Build Status](https://dev.azure.com/debauchee/Barrier/_apis/build/status/debauchee.barrier?branchName=master&jobName=Linux%20Build)](https://dev.azure.com/debauchee/Barrier/_build/latest?definitionId=1&branchName=master)|
|Mac            |[![Build Status](https://dev.azure.com/debauchee/Barrier/_apis/build/status/debauchee.barrier?branchName=master&jobName=Mac%20Build)](https://dev.azure.com/debauchee/Barrier/_build/latest?definitionId=1&branchName=master)|
|Windows Debug  |[![Build Status](https://dev.azure.com/debauchee/Barrier/_apis/build/status/debauchee.barrier?branchName=master&jobName=Windows%20Build&configuration=Windows%20Build%20Debug)](https://dev.azure.com/debauchee/Barrier/_build/latest?definitionId=1&branchName=master)|
|Windows Release|[![Build Status](https://dev.azure.com/debauchee/Barrier/_apis/build/status/debauchee.barrier?branchName=master&jobName=Windows%20Build&configuration=Windows%20Build%20Release%20with%20Release%20Installer)](https://dev.azure.com/debauchee/Barrier/_build/latest?definitionId=1&branchName=master)|
|Snap           |[![Snap Status](https://build.snapcraft.io/badge/debauchee/barrier.svg)](https://build.snapcraft.io/user/debauchee/barrier)|


### Build from source

```bash
$ git clone https://github.com/adamyordan/laplace.git
$ cd laplace && go build -o laplace main.go
$ export LAPLACE = $PATH
$ ./laplace --help
$ ./laplace -setconfig 
$ ./laplace -tls -addrs <ip address>:<port no>
```
Note: ensure you are running none using Sudo 

## Limitation 
The machine that wants to control the screen needs to either be:
- Same network as the server 
- Needs to have an IPV6 address 
- Needs to have an public IPV4 address 

## Vidoe demo

#### Video demo server side installation 
{{< youtube 7c1_jlXJW4Q >}}

#### Video demo client side installation 
{{< youtube gF70pqvN3Gk >}}



