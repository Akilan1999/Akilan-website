---
title: "IT infrastructure (Beginners guide)"
summary: Basics of running power and cheap IT infrastructure
date: 2020-05-25
aliases: ["/papermod-how-to-guide"]
tags: ["IT","Beginners"]
author: "Akilan Selvacoumar"
draft: false
aliases: [/technicalposts/beginners]
weight: 3
---


Although the current cost of IT infrastructure is relatively minimal cost these days. We can still dramatically reduce the cost further. A good IT infrastructure is the fact that we rely less on 3rd party companies and they are simple to run. When we mean simple it does mean a fancy UI where everything is drag and drop. Using a terminal can be your best friend and save you a lot of time. Like any skill you need to use it regularly to reap the benefits. It is very important to stay minimal to sustain your IT infrastructure for a longer period of time.

## Always stick to Open Source OS:
If you run a windows server then stop it. Always use an Open source OS over Proprietary. Transition is an open source OS (i.e Ubuntu , Debian) is relatively easy. To start off use a VPS to host your servers (i.e Digital Ocean, Vultr) . The main reason to use a VPS is the fact that you get an static IPV4 address. You pay for the hour rather than the month. If you think something is wrong in your server you can back it up and delete the server. Saves a lot of time on your side.

If you have an inhouse server, You can either get a static IPV4 address or use a DDNS if it is expensive (i.e so that someone can access it from outside your company network). There are many free training courses to learn how to use a linux server and configure it. This means you can be self-reliant and not rely on other companies to configure your server.

### Benefits of Open Source servers:
The main benefit is that there is no licensing cost and you have access to the source code. For Example : The linux community is really big and OS keeps getting updated frequently that means if a new vulnerability is found its most likely fixed really quick. The concept of open source OS is simple if you break it then just back up data and reinstall the OS.

## You should know Git no matter who you are:
Git is a version control system which can be used to store documents or codebase. Using it is the best way to store your company information in a secure way. It recommended you run it on your company server (Recommended to use Gitlab). If you want you can use github ( :) Owned by microsoft) .

1. [Documentation](https://git-scm.com/doc)
2. [Video](https://www.youtube.com/watch?v=2sjqTHE0zok&list=LLhy18QB1hBzZ7MniIW_FJvQ&index=6&t=0s)

## You can avoid office 365:
For your email you can set up your own mail server(i.e https://github.com/maildev/maildev) or use [Migadu](https://www.migadu.com/en/index.html) which is extremely cheap. There are so many alternatives for word , excel etc .. ( i.e LibreOffice , Apache Open Office , Google Suite etc...). If you want to have your own conference on your own server or on outside server use [Jitsi](https://jitsi.org/).

For any tool which is paid there is an open source alternative.

## Building websites:
If you are planning to have a website which is either an E-commerce website or a normal company webpage there is no point of a database like Sql unless your website is really huge. I would recommend using [static website generators](https://dzone.com/articles/6-reasons-why-you-should-go-for-a-static-website) like [Hugo](https://gohugo.io/) and either design your theme or use the ones available online. In most cases you only need to only use static generators for your company page and your basic e-commerce website.

## Deploying websites:
If you use a static website generator you can either deploy it on places like [netlify](https://www.netlify.com/) for free of cost or deploy them on your server.
