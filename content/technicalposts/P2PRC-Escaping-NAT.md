---
title: "Draft for escaping NAT with reverse proxy P2PRC"
summary: Annoying NAT boo boo
date: 2021-10-11
aliases: ["/P2PRC-escaping-NAT"]
tags: ["P2PRC","NAT"]
author: "Akilan Selvacoumar"
draft: false
aliases: [/P2PRC-escaping-NAT]
weight: 2
---

## Abstract 
We focus here on escaping NAT for the project P2PRC. The intial 
plan is to use a middle server with an IPV4 address to escape NAT. 
The future plan would be to use a WebRTC approach to where we 
use a middle server to intansiate a direct p2p connection 
using UDP sockets with nodes behind NAT. 

## Archtecture plan 
The server behind NAT would use a reverse proxy server with an IPV4 address 
to be a possible way to communicate with the outside world. 

Ex: 
```
        NAT
         |
Server  <--> Reverse Proxy server with <--> Clients 
         |   public IPV4
```

We use the libaray known as [frp](https://github.com/fatedier/frp). 
"frp is A fast reverse proxy to help you expose a local server behind a NAT 
or firewall to the internet." 

The server behind the NAT IPTable would be broadcasted through the reverse proxy.
The mapping would be done automatically though P2PRC because the reverse proxy 
could have certain ports already taken. 

We are introducting a new concept of detecting reverse proxies over P2PRC. 
We call this ``` reverse_proxy_server.json ``` and ``` reverse_proxy_mapping.json```. 

This draft is still underway :)
if you are interested to contribute email me: me AT akilan.io 
