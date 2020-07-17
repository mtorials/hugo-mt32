+++
author = "mtorials"
date = 2020-07-16T22:00:00Z
description = "How I made my multi monitor and multi gpu setup work with Manjaro Linux."
draft = true
tags = ["xorg", "manjaro", "gnu/linux", "linux"]
title = "Configuring an X Server Multi GPU Setup"

+++
# Multi GPU on Manjaro

This blog post is about how I made my multi monitor and multi gpu setup work with Manjaro Linux.

## My Setup

I use a multi monitor setup with a discrete graphics card (1050ti) and an integrated Intel HD Graphics. Manjaro, the linux distribution of my choice, offers not only proprietary Nvidia drivers but also special drivers to work with Intel and Nvidia together. Features of these special drivers called "prime" and "bumblebee" are for example power savings on laptops by using Intel graphics for lighter tasks.

The more or less unusual thing is that I have monitors connected to both my integrated as well as my discrete card.

## Where the Problems started

After I installed Manjaro and everything worked fine with the free drivers I installed the \[cuda\]([https://en.wikipedia.org/wiki/CUDA](https://en.wikipedia.org/wiki/CUDA "https://en.wikipedia.org/wiki/CUDA")) package and rebooted. After this only the monitors connected to the integrated graphics worked. I then installed the proprietary drivers for the Nvidia card. This did not solve the problem.

I went on trying different drivers. I got the to the Nvidia card connected monitors eventually to work by applying the nvidia X server configuration with this command:

    nvidia-xconfig

But then the monitors connected to the integrated graphics stayed black. I thought that I might have to configure the 