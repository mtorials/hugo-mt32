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

I use a multi monitor setup with a descrete graphics card (1050ti) and an integrated Intel HD Graphics. Manjaro, the linux distribution of my choice, offers not only proprietary Nvidia drivers but also special drivers to work with Intel and Nvidia together. Features of these special drivers called "prime" and "bumblebee" are for example power savings on laptops by using Intel graphics for lighter tasks.

## Where the Problems started

After I installed Manjaro and everything worked fine with the free drivers I installed the \[cuda\]([https://en.wikipedia.org/wiki/CUDA](https://en.wikipedia.org/wiki/CUDA "https://en.wikipedia.org/wiki/CUDA")) package and rebooted. After this only the monitors connected to the integrated graphics worked. 