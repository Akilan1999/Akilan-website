---
title: "Custom static website generator"
summary: Based on a Website generator built by
         hw tech club 
date: 2020-02-27
tags: ["Generator","Website"]
author: "Akilan Selvacoumar"
draft: false
aliases: [/technicalposts/website-generator]
weight: 2
---
In this blog post we will talk about the project custom website generator which hw tech club contributors created. Before that a bit of basics of how static website generators work. In the current scenarios websites are either rendered in the front end using React/Vue or in the backend using Jinga , express etc … The flaw in the front end is that websites use a lot of CPU memory from the Client side to load webpages and rendering on the backend does fix this issue but is still relatively more expensive than loading static web pages. A static website generator basically generates static web pages only when content is changed.

### Problems of existing Static website generators
There are many static generators such as Hugo and Jenkyll which are super efficient and do a great job in generating static web pages. The only problem is both are human readable and not Api friendly which made it initially tough for us to interact with it. Ex: Hugo has many variations and with Yaml , Toml and creating an Api to store these states and ensuring to populate according to the template was super painful for us.

### Solution
To build a simple website generator that can take a JSON file of any shape and populate it to the according website template. The only catch is that both the JSON shape and fields that should be populated in the template should be of the same shape. The implementation of this was done using Node js as that was the only language me and my friends were familiar with at that time.

![Describes a high level visualization](https://blogs.hwtech.club/images/Customwebsite.png)

### Process of generating a website
- Send Data via Rest Api
- Populate inside the appropriate template
- Copy the files modified and add it to the project directory which is created based on the project name in the JSON file.
- Respond to the user the website generated link

### Deploying generated websites in IPFS
There are bash scripts added to make it possible to deploy websites generated to IPFS (Interplanetary file system). This is to ensure that your generated website can be deployed on a peer to peer network.

The following project is released on GPLv2 hence it is completely open source and we accept contributions from all developers.

### How to contribute:
1. Create an Issue
2. Create a PR(Pull Request) linking to that issue
3. If we approve it will be merged or we will inform you on the changes we need

We have only covered the high level overview of this project and there are other modules not talked about like the whatsapp bot to interact with this Api.

- [Documentation to the project](https://website-generator.netlify.app)
- [Module of the project we are talking about in this blog](https://github.com/HWTechClub/Custom-Static-Website-Generator/tree/master/website-generator)
- [Repo Link (Main project)](https://github.com/HWTechClub/Custom-Static-Website-Generator)