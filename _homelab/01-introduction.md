---
title: "Introduction"
excerpt: "Home Lab documentation and memory dump."
permalink: /homelab/introduction/
categories:
  - Homelab
tags:
  - homelab
  - hardware
---
Since 1995 I have been running a home lab. It started with my own workstation turned into a server, running Debian Linux at the time, with services like Apache, Postfix, Bind DNS, and others running locally. In '97-'98, with an ADSL link at home, I started serving my own services, from the same server (with few upgrades). Back then I served my website, own domain DNS and e-mail servers, and other services like IRC bots, IRC server, ... 

Many changes have happened since then. At some point I moved the servers (DNS, e-mail, and web server) to VPS servers and later to cloud services. Dropped the IRC server and bots. And started using Docker for development, labs, and testing, while still maintaining a server at home for services like file sharing, backups, and other services.

In 2018 I bought three Raspberry Pi 4B and moved my home lab out of my notebook and into the Raspberry Pi cluster. The initial intention was to learn Kubernetes, using Ansible and K3S to deploy and configure the cluster. Four years later I added to the lab a Dell Optiplex that I used as a media center until I bought a smart tv. And recently I added a Lenovo ThinkCentre M90n, running Proxmox.

I am in the process of rebuilding the lab and restructuring my network. This documentation will serve as a memory dump and notebook of the entire process, with notes, configurations, and other information that I find useful to keep and may end up being helpful to others.