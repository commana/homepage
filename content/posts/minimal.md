---
title: "Minimal"
date: 2020-05-09T16:57:43+02:00
draft: true
categories:
- digital garden
tags:
- ubuntu
- linux
- i3wm
- basics
---

My minimal and distraction-free Linux development environment based on Lubuntu.

I always admired people that are super productive with their Linux environments. I've forever been a Windows and Mac user, with me occasionally trying out Linux, only to come back to my default OS because I grew frustrated with some aspect of Linux.

Would have been possible to start with an even smaller variant of Ubuntu, such as Ubuntu Server. However, my plan is to document and script as much as possible and then reinstall the system using Ubuntu Server. This will let me get rid of most of the bloatware that comes with Ubuntu's desktop versions. In addition, I was reluctant to fiddle with X11. Lubuntu serves as an easy starting point as it comes with a working window manager.

Tools I use so far:

- Lubuntu 20.04
- i3 tiling window manager
- todo.sh for simple todo management
- Firefox browser
- A bare version of vim

Monitors

(Add picture of my three monitors.)

- `sudo ubuntu-drivers autoinstall` to install drivers, esp. for my NVIDIA GeForce GTX 1050 graphics card.
- /etc/X11/xorg.conf.d/43-nvidia.conf
- Increase font size due to 4K monitor: /home/commana/.Xresources
- Set black background color on the X11 root window: /home/commana/.i3/config (after installing the nvidia drivers, the background would not reset properly and it would keep displaying the login background)

Managing Todos

- todo.sh as base w/ bash completion and alias

tmux

- Installed a plugin manager from GitHub: https://github.com/tmux-plugins/tpm downloaded to /home/commana/.tmux/plugins/tpm
- Using plugins named tmux-sensible and tmux-resurrect, which are automatically downloaded by tpm, see /home/commana/.tmux.conf
- tmux-resurrect saves sessions across reboots, so that I can keep all my projects open with their respective window layouts.
- similarly, vim session can be restored, if once types `:mksession` before closing. No plugin needed, but it needs to be enabled in .tmux.conf as well.


