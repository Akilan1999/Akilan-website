---
title: "Distributed computing in a local network"
summary: Brainstroming ideas to run distributed tasks locally
date: 2021-01-01
aliases: ["/distributed-local-network"]
tags: ["Distributed","Brainstorming"]
author: "Akilan Selvacoumar"
draft: false
aliases: [/technicalposts/distributed-local-network]
weight: 2
---


mDNS or called multicast DNS is just a DNS over a local network. mDNS is also considered as a Zero configuration technique. It can be used to discover nodes in a local network (ex: Apple’s bonjour).  

## Implementation 
- [multicast-dns](https://github.com/mafintosh/multicast-dns)
- [dns-discovery](https://github.com/mafintosh/dns-discovery)
- [libp2p-mdns](https://github.com/libp2p/js-libp2p-mdns)

Assuming all machines are running a linux kernel. All nodes in the network can have an SSH server and can broadcast each other's public key. All the nodes can add broadcasted public keys to their authorized_keys file. This is assuming it’s done in a local private network (i.e not a secure solution but an easier way). Now all nodes can SSH into each other. 

To render tasks [DrQueue](https://github.com/DrQueue/drqueue) seems to be a promising choice. DrQueue is an open source render farm system. Similar to Farmer-Joe-Render. DrQueue is used in the Visual effects ,science and finance industry. The objective of DrQueue is batch tasks and run as a task management tool for multiple nodes. DrQueue is compatible on Windows, macOS, Linux, Irix and FreeBSD. DrQueue can be used with any renderer that supports a CLI(Command Line Interface). DrQueue auto generated scripts for Blender, Maya, Lightwave, Cinema 4D, Maya, lightwave,  Mental Ray, After Effects, Aqsis, 3Delight, Pixie, Snake , Terragen and Nuke. DrQueue makes it possible to talk to master and slave nodes with a custom API which any user can create based on the inbuilt functions. 

This is just a thought in my mind of a logical and simple way to run tasks distributed. This is really important as we underestimate the computing power we have if we use our home devices collectively. We could start pushing game developers to start building games for distributed systems. Imagine if [FS2020](https://blogs.hwtech.club/post/fs2020/) could be rendered distributed :). 
