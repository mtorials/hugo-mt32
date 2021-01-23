---
title: "LinageOS 17.1: Carrier Services keeps stopping"
date: 2021-01-23
draft: true
description: "How I fixed 'Carrier Services keeps stopping' on LineageOS 17.1"
tags: ["LinageOS", "android", "sms"]
author: "mtorials"
---

# LinageOS 17.1: "Carrier Services keeps stopping"

TLDR; Disable the app "Carrier Services". Does not work? Try installing the newest version of Carrier Services from the website APKMirror; Does not work?: Disbale the just installed app Carrier Services. 

After installing LineageOS 17.1 on my Pixel 3a I had issues with sending and receiving SMS. I was rarely able to send an SMS and a received them mostly 10 minutes late. In combination with these issues I got the error "Carrier Services keeps stopping".

# Updating Carrier Services

There are quite a lot of report about this or similar behavior on the web (for example /r/LineageOS). Some people recommend updaten the app via Google Play Store. But I do not have GApps installed. So I installed the newest version version as APK from APKMirror. Still the same problem.

# Diabling Carrier Services

In the settings I noticed there was another app called CarrierDefaultApp. To give this app a chance of working i decided to disable Carrier Services and it work!

# Conculsion

I have no idea why this is a problem or what really fixed it, but maybe it helps if you have the same problem. I would recommend to disable the Carrier Services app before updating it to see weather this might do the trick on its own.
