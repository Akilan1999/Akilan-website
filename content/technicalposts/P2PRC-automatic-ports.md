---
title: "Automatic ports allocation P2PRC"
summary: Allocating ports to plugins P2PRC 
date: 2021-10-03
aliases: ["/P2PRC-Automatic-ports"]
tags: ["P2PRC","Ports","TCP","Automatic"]
author: "Akilan Selvacoumar"
draft: false
aliases: [//P2PRC-Automatic-ports]
weight: 2
---

## Automatic port allocations
P2PRC would be in-charge to set to the ports to various TCP ports 
opened. Due to this implementation the plugin being executed is 
copied to the tmp directory with a unique UUID. 
```
Command: ls /tmp
output: Semantic <UUID>_<Plugin Name> 
2e6d76c4-0ed1-4b55-9385-79a58d4f0492_p2prc-vscode-browser                
7b631e08-62ee-4c1c-a2a4-c05857b9aa7d_p2prc-vscode-browser
```
Once the copy of the plugin is added to the /tmp directory 
the site.yml file inside the appropriate yaml is modified 
with the appropriate ports assigned to the container. 

### Ex: 
1. Create container called c1 with an automatic generated TCP port 
   3313 (external) - 3313 (internal)
2. Assumption of plugin p1 exists. p1 has one server which needs to 
   be mapped to a free open TCP port in container c1. Below shows 
   an implementation of a sample site.yml file. 
```
---
- hosts: all
  tasks:
    - name: start vscode code server
      shell: sh server.sh 0.0.0.0:{{index . 0}}
```
Notice there is the following {{index . 0}}. {{index . 0}} does not belong to 
Ansible but rather is a way to mention where to add the external free port 
of the container. We use the golang [template library](https://pkg.go.dev/text/template) 
to parse and populate the site.yml with the appropriate open ports. An array of ints 
which consists of open free ports are sent to the site.yml. 0 in {{index . 0}} refers 
to the index in the int array passed on. 

After the port is automatically it's ready to run !
```
---
- hosts: all
  tasks:
    - name: start vscode code server
      shell: sh server.sh 0.0.0.0:3313
```

### Sample plugins implemented: 
- [VSCode Plugin](https://github.com/Akilan1999/p2prc-vscode-browser)


## based on PR: https://github.com/Akilan1999/p2p-rendering-computation/pull/73