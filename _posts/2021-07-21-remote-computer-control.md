---
layout: post
title: Setting up full remote control on my main computer
date: 2021-07-21
categories: [blog]
tags: [remote control, cloud gaming]

excerpt: Configuring my desktop computer to have full remote control over it and make
  it a personal cloud gaming station.
---

## Motivation

A busy year at school ends, and so I wanted to do something cool with the free
time I had. I was thinking about the coming vacation I might have and, while
the idea of moving to a remote area enjoying the sun in the summer and the pure
air near the sea sounds great, the idea of leaving my desktop computer at
home annoyed me.

Why? Because I'd like to keep having the option to access it and keep playing
any games I want during my vacation, regardless of where I am. I'm lucky to
have a good laptop computer, but it's not great for playing games because of
its weaker specs compared to my desktop computer.

But you know what's hype nowadays to play anywhere? Cloud gaming! So what if
could configure my desktop computer to have full remote control over it? Sounds
like a great solution for me.

So I started thinking about it and came up with three objectives:

- Being able to play games remotely, ideally via the Steam Link software.
- Being able to have full remote control over my computer, almost as if I was
  actually using it physically.
- Being able to turn off and on my computer remotely with Wake-On-LAN, so that
  it doesn't have to stay on all day and night for this to work.

Then I got started.

## Playing games remotely

The Steam client is great as it easily allows playing a game on a device by
streaming it from a PC with the game installed. That seemed to work as long as
the PC and the devices are both connected on the same local network, allowing
Steam to automatically detect the games available on the computer.

Considering this, I thought that being connected on the same local network was
a requirement for [Steam Remote Play][1] to work. Therefore, I thought of a solution
and I looked up how to setup an OpenVPN server at home using a
[Raspberry Pi 3][2].

[1]: https://store.steampowered.com/remoteplay#anywhere
[2]: https://www.raspberrypi.org/products/raspberry-pi-3-model-b/

The idea is that even if I'm not home, I could connect to my VPN server and
trick Steam into thinking I'm connected on the same local network as my desktop
computer and allow it to detect the games installed on it.

I dusted out my Raspberry Pi 3, did a fresh installation of Rasbian on it, and
installed an [OpenVPN][3] server with [PiVPN][4]. I also configure a DNS record to
point to it for easier access.

[3]: https://openvpn.net/
[4]: https://pivpn.io/

Then, I installed the OpenVPN Connect application on my laptop computer and it
worked! While connected on the 4G celular network via my phone, I was able to
stream games via Steam as long as I was connected to my VPN server.

I also tested this on my phone directly using the OpenVPN Connect and Steam
Link Android applications, and it worked as well! However, I found on my phone
that being connected to my VPN server was actuallt not required. The only
requirement for the Steam Link app to work is that I have to manually pair it
with my desktop computer first, then everything would work regardless of the
network I'm connected to.

So I was kinda disapointed. I also installed the Steam Link application on
Windows and found that it also worked fine after pairing it, regardless of the
network. However, I still had to configure Wake-On-LAN later so I kept the
VPN server running for later.

The first objective is completed! As a bonus, the Steam Link application
allows not only for playing games, but also for remote control over the entire
computer (even if it's far from ideal).

## Turning off and on my computer remotely

Configuring [Wake-On-LAN][5] is something I already did in the past so I just has to
verify my network adapter settings and my BIOS settings.

[5]: https://en.wikipedia.org/wiki/Wake-on-LAN

I shut down my desktop computer, and I installed an application on my laptop to
send Wake-On-LAN packets and test my configuration. It was a success as I was
able to wake up my desktop computer while being connected on the same local
network or connected to my VPN server.

## Improving full remote control

While Steam Link allowed for some kind of full remote control, it was not
ideal. Therefore, I chose to rely on an application I've used many times for
this: [TeamViewer][6].

[6]: https://www.teamviewer.com/en/

I installed it on my desktop computer and configured it. I made sure it would
automatically starts with Windows and it is associated with my TeamViewer
account so I can access it easily.

While digging in the configuration, I noticed a setting to enable some king of
Wake-On-LAN via TeamViewer over a public address. So I configured another DNS
record to point to my home network and enabled that.

I tested it from the TeamViewer application on both my laptop and my phone, and
I was able to wake up my desktop computer and have full remote control over it.

This rendered my VPN server somewhat useless so, sadly, I shut that down.

## A successful endeavor

This is a success! I was able to configure my desktop computer as my cloud
gaming station after completing all of my objectives:

- Steam Link allows me to play remotely.
- TeamViewer allows me to have full remote control over my computer.
- TeamViewer allows me to remotely wake up my computer.

Also, even though the VPN server I've set up proved to be useless despite what
I thinking, I'm happy with the results and all of this has still been good
practice for me.
