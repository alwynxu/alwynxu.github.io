---
title: ubuntu和redhat网络配置
---

<!--more-->
## 1. ubuntu14网络配置
``` 
cd /etc/network/
vim interfaces
```

```
# This file describes the network interfaces available on your system
# and how to activate them. For more information, see interfaces(5).

# The loopback network interface
auto lo
iface lo inet loopback

# The primary network interface
auto eth0
iface eth0 inet dhcp

# 添加网络配置
auto eth1
iface eth1 inet static
        address 192.168.56.101
        network 192.168.0.0
        netmask 255.255.255.0
        gateway 192.168.0.1

```

## 2. redhat网络配置
配置文件位于: `/etc/sysconfig/network-scripts/`
编辑文件 ： `vim ifcfg-eth0 `
```
DEVICE=eth0
HWADDR=08:00:27:84:ba:8b
TYPE=Ethernet
UUID=ef3bdd7e-fc7f-43cd-b057-536128da39fe
ONBOOT=yes
BOOTPROTO=dhcp
IPADDR=192.168.56.102
GETWAY=192.168.0.1
PREFIX=24
DNS=192.168.1.1 
NETMASK=255.255.255.0
```
重启服务：`servie network restart`
