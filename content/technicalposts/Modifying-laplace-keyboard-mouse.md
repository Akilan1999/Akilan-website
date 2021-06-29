---
title: "Using remote ScreenShare ,keyboard and mouse using laplace and Barrier"
summary: Modifying the open source project laplace to allow remote keyboard and mouse during screenshare
date: 2020-05-25
aliases: ["/laplace-keyboard-mouse"]
tags: ["WebRTC","laplace"]
author: "Akilan Selvacoumar"
draft: true 
aliases: [/laplace-keyboard-mouse]
weight: 2
---

## What is laplace ?
" Laplace is an open-source project to enable screen sharing directly via browser. Made possible using WebRTC for low latency peer-to-peer connections, and WebSocket implemented in golang for WebRTC signaling. "

link: https://github.com/adamyordan/laplace

## How to set up laplace ? 

You need to ensure that you have the go compiler installed in your machine.
```
> go version
> git clone https://github.com/adamyordan/laplace
> cd laplace 
> go build . 

// Run laplace 
> ./laplace 
```
When running the default port it's using is port 443 with a https connection

#### Ex: https://0.0.0.0:443





