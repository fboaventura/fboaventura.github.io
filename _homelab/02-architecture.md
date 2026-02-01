---
layout: single
title: "Architecture"
excerpt: "Home Lab architecture, equipments, and diagrams."
permalink: /homelab/architecture/
categories:
  - Homelab
tags:
  - homelab
  - architecture
  - hardware
classes:
  - landing
  - dark-theme
toc: true
toc_sticky: true
toc_label: "Table of Contents"
toc_icon: "cog"
---
The homelab is composed of a few devices, some of them are part of the lab, others are part of the network, and others are part of the house. The lab is composed of a Raspberry Pi cluster, a Dell Optiplex, and a Lenovo ThinkCentre M90n. The network is composed of a switch, a firewall, two routers, and a few access points.

## Diagram

The diagram below shows the architecture of the homelab and the network.

{% include figure popup=true image_path="/assets/images/homelab/homelab-diagram.png" alt="Home Lab Diagram" caption="The Home Lab" %}

## Raspberry Pi Cluster

The Raspberry Pi cluster is composed of three Raspberry Pi 4B, with 4GB of RAM each, and a 500Gb SSD connected to each of them. The cluster is running K3S, a lightweight Kubernetes distribution, and is used for development, testing, and learning purposes.

### RPi1

| Property           | Value                      |
|--------------------|----------------------------|
| Hostname           | rpi01                      |
| Operating System   | Linux 6.8.0-1016-raspi     |
| Kernel Version     | #18-Ubuntu SMP PREEMPT_DYNAMIC Fri Nov 22 11:55:16 UTC 2024 |
| Architecture       | aarch64                    |
| CPU                | Cortex-A72                 |
| CPU Cores          | 4                          |
| Logical CPUs       | 4                          |
| Total RAM          | 3.74GB                     |
| Swap Memory        | 0.00B                      |
| Disk Hardware      | sda (ASMT1051: 465,8G)<br> mmcblk0: 119,1G |
| Disk Partitions    | /dev/mmcblk0p2 (/): 116.69 GB<br> /dev/mmcblk0p1 (/boot/firmware): 0.49 GB |
| Network Devices    | wlan0                      |
| IP Address         | 10.102.0.254/24            |
| IP Addresses       | 10.102.0.254/24            |

### RPi2

| Property           | Value                      |
|--------------------|----------------------------|
| Hostname           | rpi02     |
| Operating System   | Linux 6.8.0-1016-raspi     |
| Kernel Version     | #18-Ubuntu SMP PREEMPT_DYNAMIC Fri Nov 22 11:55:16 UTC 2024 |
| Architecture       | aarch64                    |
| CPU                | Cortex-A72                 |
| CPU Cores          | 4                          |
| Logical CPUs       | 4                          |
| Total RAM          | 3.74GB                     |
| Swap Memory        | 0.00B                      |
| Disk Hardware      | sda (ASMT1051: 465,8G)<br> mmcblk0: 119,1G |
| Disk Partitions    | /dev/mmcblk0p2 (/): 116.69 GB<br> /dev/mmcblk0p1 (/boot/firmware): 0.49 GB |
| Network Devices    | wlan0                      |
| IP Address         | 10.102.0.179/24            |
| IP Addresses       | 10.102.0.179/24            |

### RPi3

| Property           | Value                      |
|--------------------|----------------------------|
| Hostname           | rpi03                      |
| Operating System   | Linux 6.8.0-1016-raspi     |
| Kernel Version     | #18-Ubuntu SMP PREEMPT_DYNAMIC Fri Nov 22 11:55:16 UTC 2024 |
| Architecture       | aarch64                    |
| CPU                | Cortex-A72                 |
| CPU Cores          | 4                          |
| Logical CPUs       | 4                          |
| Total RAM          | 3.74GB                     |
| Swap Memory        | 0.00B                      |
| Disk Hardware      | sda (00SSD1: 465,8G)<br> mmcblk0: 119,1G |
| Disk Partitions    | /dev/mmcblk0p2 (/): 116.69 GB<br> /dev/mmcblk0p1 (/boot/firmware): 0.49 GB |
| Network Devices    | wlan0                      |
| IP Address         | 10.102.0.146/24            |
| IP Addresses       | 10.102.0.146/24            |


## Dell Optiplex (bell)

The Dell Optiplex is a small form factor desktop computer, with an Intel Core i5, 16GB of RAM, and a 1Tb SATA SSD and 1Tb M2 SSD. It is used as a media center, running Kodi, and as a backup server, running BorgBackup.

This server runs CasaOS and is used to run a few services. Part of the process of rebuilding the lab is to move the services running on this server either to containers or to virtual machines running on the Proxmox server.

| Property           | Value                      |
|--------------------|----------------------------|
| Hostname           | bell                       |
| Operating System   | Linux 6.8.0-51-generic     |
| Kernel Version     | #52-Ubuntu SMP PREEMPT_DYNAMIC Thu Dec  5 13:09:44 UTC 2024 |
| Architecture       | x86_64                     |
| CPU                | Intel(R) Core(TM) i3-9100T CPU @ 3.10GHz |
| CPU Cores          | 4                          |
| Logical CPUs       | 4                          |
| Total RAM          | 15.43GB                    |
| Swap Memory        | 32.00GB                    |
| Disk Hardware      | sda (CT1000BX500SSD1: 931,5G)<br> nvme0n1 (CT1000P3PSSD8: 931,5G) |
| Disk Partitions    | /dev/nvme0n1p2 (/): 883.79 GB<br> /dev/nvme0n1p1 (/boot/efi): 1.05 GB<br> /dev/sda1 (/DATA): 915.82 GB |
| Network Devices    | enp1s0<br> vlan.2<br> br-1c1bd8cb80ac<br> docker0<br> br-62dcf5575556<br> br-6515792d9548<br> br-79d918432784<br> br-de7120fd41a7<br> br-1467a7c76a9a<br> br-19906c4913c1<br> br-a36af62986cd<br> br-a5df829f691d<br> br-0a4101090a0f |
| IP Address         | 192.168.18.2/24            |
| IP Addresses       | 192.168.18.2/24<br> 10.102.0.2/24<br> 172.24.0.1/16<br> 172.17.0.1/16<br> 172.31.0.1/16<br> 172.21.0.1/16<br> 172.22.0.1/16<br> 172.20.0.1/16<br> 172.18.0.1/16<br> 172.26.0.1/16<br> 172.23.0.1/16<br> 172.29.0.1/16<br> 172.25.0.1/16 |

## Lenovo ThinkCentre M90n (baklouti)

The Lenovo ThinkCentre M90n is a small form factor desktop computer, with an Intel Core i5, 16GB of RAM, a 1Tb SATA SSD and a 1Tb NVMe SSD. It is running Proxmox, a hypervisor based on Debian, and is used to run virtual machines and containers.

| Property           | Value                      |
|--------------------|----------------------------|
| Hostname           | baklouti                   |
| Operating System   | Linux 6.8.12-5-pve         |
| Kernel Version     | #1 SMP PREEMPT_DYNAMIC PMX 6.8.12-5 (2024-12-03T10:26Z) |
| Architecture       | x86_64                     |
| CPU                | Intel(R) Core(TM) i5-7500T CPU @ 2.70GHz |
| CPU Cores          | 4                          |
| Logical CPUs       | 4                          |
| Total RAM          | 15.51GB                    |
| Swap Memory        | 8.00GB                     |
| Disk Hardware      | sda (CT1000BX500SSD1: 931,5G)<br> sdb (SPZX-35Z10T0: 931,5G) |
| Disk Partitions    | /dev/mapper/pve-root (/): 93.93 GB |
| Network Devices    | wlp1s0<br> vmbr0           |
| IP Address         | 192.168.18.3/24            |
| IP Addresses       | 192.168.18.28/24<br> 192.168.18.3/24 |


## Network

### Internet Links

The house has two internet links used in a failover configuration. Both links are fiber links with 750Mbps download and 150Mbps upload. The links are connected to an Ubiquiti UCG Ultra, working as a firewall and responsible for load balancing the links, partitioning the network into VLANs, and managing the Wireless networks and SSIDs.

### Switch

The network switch is a small 1Gb L2 TP-Link switch, with 8 ports, used to connect the devices in the lab and the network.

### Access Points

The house has four Ubiquiti AP-U6-Mesh access points, providing wireless coverage to the entire house. The access points are connected to the switch and managed by the Ubiquiti UCG Ultra. There are three SSIDs, one for the main network, one for guests, and one for the lab, witch is also connected to a cabled VLAN.


## Subnets

{% include figure popup=true image_path="/assets/images/homelab/subnets_detail.png" alt="Home Lab Subnets Details" %}