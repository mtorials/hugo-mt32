---
title: "Setting up my server"
date: 2021-03-20
draft: false
description: "This is about my new VPS setup and what issues I ran into."
tags: ["server", "deployment", "vps", "docker"]
author: "mtorials"
---

# My own server

Hi! In this post I want to write about some decision regarding my new VPS installation. Maybe you find it helpful!

## System and configuration

As my operating system I chose Debian. It is a very stable Linux distribution and you can find a lot of support on the web.
For the basic setup I also install ZSH, a shell, just because I find it nice and more convenient than bash. As first and very basic step I installed a firewall
and 

* Debian
* ZSH and Oh My ZSH
* UFW Firewall

## What I run

Here is a list of some servers and programmes I use on my server. There are programmes that run containerized and some run on the host machine.
On the host there are:

* Docker itself
* NGINX for static files and as reverse proxy for the docker containers
    * serving this blog and mtorials.de
* Certbot for configuring Let's Encrypt SSL

And containerized:

* Synapse, matrix homeserver
* PostgreSQL database
* Portainer to manage the containers
* GitLab for some CI/CD
* personal projects based on jvm (mtstats, dialbot)
* Nextcloud, a - yes - cloud
* Searx, a meta search engine
* Netdata for monitoring

## Issues

Most of these programmes are pretty straight forward to set up, but I ran into some problems.

### Firewall and Docker

As I said before one of my first steps was to install the UFW firewall. I configured it to open ports 22, 80 and 443 only. But when I port scanned my server there were a lot more ports open. My first thought was that I had misconfigured UFW, but I could not find any mistake and it seemed ok. After I bit of research online I decided to search for this problem in the context of docker. There was really no real reason to do so, but all the ports that were open were ports exposed by docker containers. But I also had no servers on the host that could have exposed ports.

Very quickly I found this [issue](https://github.com/docker/for-linux/issues/690) and it seems like docker just overwrites the rules you set with UFW. There were many people complaining about this behavior in this issue thread and it is definitely something you have to be aware of to not have a big security flaw in your setup. So [here](https://github.com/chaifeng/ufw-docker) I found a fix.

# Conclusion

This is not really a complete article and there where more issues I will not talk about in this post. But maybe this is still interesting a least for me when I break my server the next time...

mtorials