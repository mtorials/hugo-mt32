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

_*Disclamer: This is how I was able to fix this problem. This may work for other, but I can not guarantee this. This is NOT a guide!*_

## My Setup

I use a multi monitor setup with a discrete graphics card (1050ti) and an integrated Intel HD Graphics. Manjaro, the linux distribution of my choice, offers not only proprietary Nvidia drivers but also special drivers to work with Intel and Nvidia together. Features of these special drivers called "prime" and "bumblebee" are for example power savings on laptops by using Intel graphics for lighter tasks.

The more or less unusual thing is that I have monitors connected to both my integrated as well as my discrete card.

## Where the Problems Started

After I installed Manjaro and everything worked fine with the free drivers I installed the \[cuda\]([https://en.wikipedia.org/wiki/CUDA](https://en.wikipedia.org/wiki/CUDA "https://en.wikipedia.org/wiki/CUDA")) package and rebooted. After this only the monitors connected to the integrated graphics worked. I then installed the proprietary drivers for the Nvidia card. This did not solve the problem.

I went on trying different drivers. I got the to the Nvidia card connected monitors eventually to work by applying the nvidia X server configuration with this command:

    nvidia-xconfig

But then the monitors connected to the integrated graphics stayed black. I thought that I might have to configure the X server myself. This \[forum post\]([https://forum.manjaro.org/t/how-to-add-a-second-monitor-connected-to-the-integrated-graphics-card-not-the-dedicated-one/107158](https://forum.manjaro.org/t/how-to-add-a-second-monitor-connected-to-the-integrated-graphics-card-not-the-dedicated-one/107158 "https://forum.manjaro.org/t/how-to-add-a-second-monitor-connected-to-the-integrated-graphics-card-not-the-dedicated-one/107158")) confirmed that.

## Fixing Parts

In copied the Nvidia configuration file and copied it from /etc/X11/xorg.conf to /etc/X11/xorg.conf.d/, renamed the old file so that it would not take any effect and modified the new one.

    sudo cp /etc/X11/xorg.conf /etc/X11/xorg.conf.d/myconfig.conf
    sudo mv /etc/X11/xorg.conf /etc/X11/xorg.conf.old
    sudo nano /etc/X11/xorg.conf.d/myconfig.conf

I copied the "Device" section and then edit it to make it look like this:

    Section "Device"
        Identifier     "Device1"
        Driver         "intel"
        VendorName     "Intel Corporation"
        BusID          "PCI:00:02.0"
    EndSection

I found the bus ID of the Intel graphics with the command:

    inxi -Fx

I now had two devices in my xorg config. And this was the fix!

Sometimes you have to also enable the monitors. I was able to this with the graphical tool in Manjaro, but you should be able to use xrandr for this.

## Troubleshooting

If you want to know whether your second device (graphics (card)) is detected or not, you can use

     xrandr --listproviders

## Problems Remaining

I sadly was not able to rotate my monitor connected to the integrated graphics. It resulted in inconsistent and strange behavior while not filling the screen space with content. I eventually "fixed" this by rotating the monitor back to its normal rotation.

## Conclusion

Windows handles it better...... But maybe this was still helpful to you! If not, it will be for my future me.