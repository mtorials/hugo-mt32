---
title: "Linux Customization on Arch with i3wm"
date: 2021-03-20
draft: true
description: "How I customized my linux desktop with arch and the i3 window manager!"
tags: ["linux", "arch", "polybar", "customization", "i3wm"]
author: "mtorials"
---

# Linux Customization on Arch with i3wm

I recently started to tinker with my Linux desktop. There are a lot of different things that I learned along the way and in this article I want write them all down.

Everything that I talk about in this article is available on [github](https://github.com/mtorials/dotfiles) and my [gitlab](https://git.mt32.net/mtorials/mtorials-configs)!

## Starting out

For years now I used Manjaro Linux with XFCE on my laptop and desktop. Manjaro is in my opinion already one of the best themed distros out there, so I only normally only change a few things like the wallpaper and the panel (bar).

My journey started when I wanted to have blur. I really like the look of transparent and blurred terminals and panels. XFCE has a compositor build in and you can change quit a bit there, but there is no option for blur. So I decided to change the compositor to Picom.

## Picom

[Picom](https://github.com/yshui/picom) is a compositor for X11 and can be used with XFCE. As with many open source software projects it is something like a fork of a fork of a fork or similar. So I decided to use a fork of Picom! [The fork I use](https://github.com/ibhagwan/picom) supports not only blurring the background but also rounded corners for windows. I will come back to these later!

## Polybar

Polybar is - as the name implies - a bar (panel). The really cool thing about it compared to for example the xfce panel is that you can write your own scripts for it. The output of a command will then be displayed. This perfectly represents the UNIX philosophy and makes "a polybar" quite extensible. Take this for example:

```sh
curl -s https://api.github.com/users/mtorials | jq '.followers'
```

This very short script outputs the my github follower count, 5... With a few lines of config we can write our own Polybar module out of this and watch my - or your - follower count fo up - or down.

```ìni
[module/githubcounter]
type = custom/script
exec = curl -s https://api.github.com/users/mtorials | jq '.followers'
click-left = firefox https://github.com/mtorials
interval = 10
```

This module will output the follower count on github and check it every 10 seconds and when you left click it, it opens firefox with my github profile. The possibilities are endless and it enables you to show and execute everything you could also do with the command line.

I use polybar to display the current workspace, show the currently playing song and manage my audio. All with the help of scripts!