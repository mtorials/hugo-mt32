---
title: "Setting up my Server"
date: 2021-01-10
draft: true
description: "This is about my new VPS setup and what issues I ran into."
tags: ["server", "deployment", "vps", "docker"]
author: "mtorials"
---

# My own server

## System and configuration

As my operating system I chose Debian. It is a very stable Linux distribution and you can find a lot of support on the web.
For the basic setup I also install ZSH, a shell, just because I find it nice to have and I setup a firewall.

* Debian
* ZSH and Oh My ZSH
* UFW Firewall

## What I want to run

Here is a list of some servers and programms I use on my server. There are programms that run containerized and some run on the host maschine.
On the host there are:

* docker itself
* nginx for static files and as reverse proxy
    * serving this blog and mtorials.de
* certbot for configurating Let's Encrypt SSL

And containerized:

* matrix homeserver synapse or dendrite
* postgresql database
* portainer to manage the containers
* GitLab
* personal projects based on jvm (mtstats, dialbot)
* next cloud
* searx meta search engine
* netdata monitoring

## Issues

Most of these programms are pretty straight forward to set up, but I ran into some problems.

### Firewall and Docker

As I said before one of my first steps was to install the UFW firewall. I configured it to open ports 22, 80 and 443 only. But when I portscanned my server there were a lot more ports open. My first thought was that I had misconfigured UFW, but I could not find a mistake and it seemed ok. After I bit of searching online I decieded to search for this problem in the context of docker. There was really no real reason to do so, but all the ports that were open were ports exposed by docker containers. But I also had no servers on the host that could have exposed ports.

Very quickly I found this [issue](https://github.com/docker/for-linux/issues/690) and it seems like docker just overrites the rules you set with UFW. There were many people complaining about this behavior in thi issue thread and it is defenetly something you have to be aware of to not have a big security flaw in your setup. So [here](https://github.com/chaifeng/ufw-docker) I found a fix.

### IP Adresses of Docker containers change