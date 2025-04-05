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

## Architecture plan 
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
The ```reverse_proxy_server.json``` file is incharge of detecting all reverse 
proxy servers and the ```reverse_proxy_mapping.json``` is incharge of logging 
all the reverse proxy server mappings talking place. 

#### reverse_proxy_server.json
```
{
   "reverse_proxy_servers": [
           {
                   "Server_name": <server name>,
                   "Address": <remote address>,
                   "Latency": <latency>
           }, ... n
   ]
}
```

#### reverse_proxy_mapping.json
```
{
   "reverse_proxy_mappings": [
           {
                   "Server_name": <server name>,
                   "Address": <remote address>,
                   "Type": <TCP or UDP>,
                   "blind_port": <port no>
           }, ... n
   ]
}
```

### Port allocation 
The function for port allocation would need certain 
modifications need to ensure that the port is not only free 
on the server but also on the on reverse proxy server. 
We are debate on this would occur as it requires 
further reading on the inner depths of [frp](https://github.com/fatedier/frp).
The idea scenario would be that the odds a 5 or 6 digit 
taken is a low probability. 

### How would the ip tables would look
There would not be much change when a client looks 
at it. This only difference is that the client 
see's the address of the proxy server.

Ex: 
```
{
 "ip_address": [
  {
   "ipv4": "<reverse proxy address>",
   "ipv6": "",
   "latency": 0,
   "download": 0,
   "upload": 0,
   "serverport": "<server port no>"
  }
 ]
}
```

If the server is using a reverse proxy then the server 
port no should be decided by P2PRC to ensure that there 
is no scenario where the port is already taken. 

## New Cli Commands
We will be introducing a new set of Cli commands. 
These cli commands would be incharge to starting 
the reverse proxy or connecting to the reverse proxy 
and various other function. 

1. start reverse proxy (need public IPV4)
```
p2prc -s --reverse-proxy
```
This will start the reverse 
and autoamtically broadcast 
as a reverse proxy as well. 

2. connecting to a reverse proxy 
```
p2prc -s --connect-reverse-proxy <proxy ip address>
```
This will start p2prc as server 
and automatically set the server port 
and link it to the reverse proxy and 
any connections would go through the 
reverse proxy. 

3. Listing all proxy servers avaliable 
```
p2prc --view-rps or p2prc --view-reverse-proxy-servers
```

4. Listing all reverse proxy connection mapping 
```
p2prc --view-rpm or p2prc --view-reverse-proxy-mapping 
```

