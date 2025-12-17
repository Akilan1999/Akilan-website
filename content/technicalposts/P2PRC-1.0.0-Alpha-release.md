---
title: "Alpha Release P2PRC v1.0.0"
summary: Alpha release for P2PRC
date: 2021-06-27
tags: ["P2PRC","v1.0.0-alpha"]
author: "Akilan Selvacoumar"
draft: false
aliases: [/p2prc-1.0.0-alpha]
weight: 2
---

After 5 months of working on this project. I would be glad to announce that we 
have a alpha release. The objective of P2PRC is to create a p2p network where nodes 
can share each others computatination power in a virtualized manner (i.e digital 
ocean where anyone can share resources). In the alpha release the choice of
virtualization used is docker. The current release will 
support docker. It should be noted that from the next release onwards we will 
not support the docker daemon. We will try to provide backwards compatability 
as much as we can but I have decided to ditch the docker daemon and write 
compatable code from containerd. 

## Major features 
- IPV4 and IPV6 support: All the nodes can listen to both IPV4 and 
IPV6 addresses. It can be noted that with IPV6 there are minor issues 
detected in certain PC in terms of SSH into a docker container which is 
mostly on the server side. 

- Hopping mechanism: Since it's a p2p network we have a very simple 
implementation that hops though servers and downloads it's IP tables.
In our implementation. This contains about imformtaion of other servers 
in the network. This way nodes can automatically learn parts of the 
network. The current implementation uses 3 hops. 

- Possibility to run any docker container: To satisfy this the server 
must already have the docker container and the must ensure that the 
SSH username is 'master' and password is 'password' in creation of new 
servers. It's not secure but worksout for this version for now. 

The test network will be avaliable for use from the beta release 
which should come out on the 5th of july 2021. The network will 
consist of 1 node which runs on a paid cloud server as I do not 
keep my machines on 24/7. The node up will help to connect with 
other nodes and the paid cloud server cannot be used to create 
and remove containers.

### Link to release and installation instructions:
https://github.com/Akilan1999/p2p-rendering-computation/releases/tag/v1.0.0-alpha


