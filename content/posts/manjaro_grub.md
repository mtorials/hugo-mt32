---
title: "Manjaro: How to fix GRUB OS selection not showing up or no other OSs"
date: 2021-01-23
draft: false
description: "After an update the GRUB boot manager did not want to show up after starting the system. That meant that I could only boot Manjaro. Here is the fix."
tags: ["Manjaro", "grub", "linux"]
author: "mtorials"
---

# Manjaro: How to fix GRUB OS selection not showing up or no other OSs

After an update the GRUB boot manager did not want to show up after starting the system. That meant that I could only boot Manjaro.

To fix this open /etc/default/grub with:

```sh
sudo nano /etc/default/grub
```

If you see no GRUB screen at all on boot comment the line GRUB_TIMEOUT_STYLE=hidden so that it looks like this:

```txt
#GRUB_TIMEOUT_STYLE=hidden
```

To make sure GRUB detects the OSs installed on your machine add the line:

```txt
GRUB_DISABLE_OS_PROBER=false
```

Then exit nano with CTRL+O and CTRL+X.
After this update grub with 

```sh
sudo update-grub
```

(It can take a while). Now just reboot!

## Manually checking for OSs

If you want to manually check for OSs on your machine use:

```sh
sudo os-proper
```

## Source

A very helpful reddit thread: https://www.reddit.com/r/ManjaroLinux/comments/m2pe6o/boot_menu_doesnt_appear_when_switching_on_computer/
Also if it does not work check out: https://endeavouros.com/docs/installation/grub-booting-other-systems/
