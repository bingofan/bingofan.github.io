---
title: WiFi 笔记完善计划
toc: true
description:
	'系统整理WiFi相关的内容'
tags:
	嵌入式
	WiFi
categories:
	wiki-WiFi
---

### WiFi概念
定义 : `Wi-Fi` / `WiFi` (/ˈwaɪ faɪ/) 
[WiFi维基百科](https://en.wikipedia.org/wiki/Wi-Fi)
Wi-Fi是一种允许电子设备连接到一个无线局域网（WLAN）的技术，通常使用2.4G UHF或5G SHF ISM 射频频段。连接到无线局域网通常是有密码保护的；但也可是开放的，这样就允许任何在WLAN范围内的设备可以连接上。Wi-Fi是一个无线网络通信技术的品牌，由Wi-Fi联盟所持有。

### WiFi联盟
Wi-Fi联盟（全称：国际Wi-Fi联盟组织），英语：Wi-Fi Alliance，简称WFA），是一个商业联盟，拥有 Wi-Fi的商标。
![Wi-Fi联盟图标](\images\wiki\wiki-wifi\Wi-Fi_Alliance_Logo.svg.png)

### 802.11协议

### mac80211
[mac80211官方文档](https://wireless.wiki.kernel.org/en/developers/Documentation/mac80211)


### nl80211 & cfg80211
   	+-------------+
    |             |
    |  Userspace  |
    |             |
    +-------------+
          ^
    - - - | - - -     
          | nl80211
          v
    +-------------+
    |             |
    |  cfg80211   |
    |             |
    +-------------+
    +-------------+
    |             |
    |  mac80211   |
    |   driver    |
    |             |
    +-------------+

nl80211 / cfg80211 / mac80211不再使用的ioctl，他们使用 netlink (译者注：基于 socket 通信)

### Netlink

定义: [`Netlink`维基百科](https://en.wikipedia.org/wiki/Netlink)

像 `iw`, `hostapd` 或 `wpa_supplicant` 之类的工具使用一些`Netlink`的库
`Netlink`的库:
* [libnl](http://www.carisma.slowglass.com/~tgr/libnl/)
  [官方文档](http://www.carisma.slowglass.com/~tgr/libnl/doc/core.html)
* [libnl-tiny](https://dev.openwrt.org/browser/trunk/package/libs/libnl-tiny)

### iw
iw 是一种新的基于`nl80211`的用于无线设备的CLI(客户端)配置实用程序。
iw 的出现是为了替换掉旧的iwconfig工具.

*　iw 官方文档 [https://wireless.wiki.kernel.org/en/users/documentation/iw](https://wireless.wiki.kernel.org/en/users/documentation/iw)
*　iw 发布压缩包下载地址 [https://www.kernel.org/pub/software/network/iw/](https://www.kernel.org/pub/software/network/iw/)
* iw git项目地址 [http://git.kernel.org/?p=linux/kernel/git/jberg/iw.git](http://git.kernel.org/?p=linux/kernel/git/jberg/iw.git)

**iw使用**
获得所有设备的功能，如带宽信息（2.4GHz，和5GHz），和802.11n的信息
``` shell
iw list
```
·
扫描
``` shell
iw dev wlan0 scan
```
·
监听事件
只要使用 
```shell
iw event
```
·
调试时观察`auth`/`assoc`/`deauth`/`disassoc`帧
使用
``` shell
iw event -f
```
·
时间信息：
``` shell
iw event -t
```
·
获得链路状态
为了确定您是否连接到一个`AP`上，如果你是最后一个使用的发送速率，您可以使用下面的命令。
关联到传统（非`802.11n`标准）的AP的输出示例：
``` shell
iw dev wlan0 link
Connected to 04:21:b0:e8:c8:8b (on wlan0)
        SSID: attwifi
        freq: 2437
        RX: 2272 bytes (18 packets)
        TX: 232 bytes (3 packets)
        signal: -57 dBm
        tx bitrate: 36.0 MBit/s
```
·
关联到`802.11n`的`AP`的输出示例：
``` shell
iw dev wlan0 link
Connected to 68:7f:74:3b:b0:01 (on wlan0)
        SSID: tesla-5g-bcm
        freq: 5745
        RX: 30206 bytes (201 packets)
        TX: 4084 bytes (23 packets)
        signal: -31 dBm
        tx bitrate: 300.0 MBit/s MCS 15 40Mhz short GI
```
·
当输出没有连接到一个`AP`:
``` shell
iw dev wlan0 link
Not connected.
```
·

要连接到一个AP可以使用
``` shell
iw connect
```
如果连接要求： 
* 无加密
* 使用WEP加密
{% alert warning %}
如果你需要连接到一个`AP`要求使用`WPA`或`WPA2`，那么你必须使用`wpa_supplicant` 。
{% endalert %}

**建立基本连接**
你可以使用iw直接连接到一个`AP`上，当且仅当`AP`：
*　无加密
* 使用WEP加密

连接到开放的`AP` `SSID`是`foo` ： 
``` shell
iw wlan0 connect foo
```
·
指定使用的频率(可能有同名SSID,这时需要指定频率)： 
``` shell
iw wlan0 connect foo 2432
```
·
连接`WEP`的`AP`：
``` shell
iw wlan0 connect foo keys 0:abcde d:1:0011223344
```
·
**获取`station`统计数据**
要获取`station` 的统计信息，如
发送/接收的字节，最后发送的比特率（包括MCS率）：
``` shell
$ iw dev wlan1 station dump
Station 12:34:56:78:9a:bc (on wlan0)
        inactive time:  304 ms
        rx bytes:       18816
        rx packets:     75
        tx bytes:       5386
        tx packets:     21
        signal:         -29 dBm
        tx bitrate:     54.0 MBit/s
```
·
获得`station`对应的`peer`统计信息：
``` shell
sudo iw dev wlan1 station get <peer-MAC-address>
```
·
在`STA`的情况下，上述的`<peer-MAC-address>`将是你的`AP`的`MAC`地址。

**修改传输比特率**
`iw` 支持修改发送的比特率，假托传统和 `HT MCS`速率。
 这是通过设定允许的比特率掩码来实现，你也可以清除该掩码。
修改`TX`传统的比特率
设定用于使用某些传统的比特率传输的性能。 ：
``` shell
iw wlan0 set bitrates legacy-2.4 12 18 24
```
·
使能“`Purge G`”来禁用`802.11b` 关联：
``` shell
iw wlan0 set bitrates legacy-2.4 6 12 24
```
·
修改`tx HT MCS`的比特率
设置使用`MCS`率传输的能力是通过让你指定**频段**和**MCS率**来实现。
注意，是否该设备实际上监听你的请求将根据设备驱动程序和固件的配合而变化。 例如：
``` shell
iw dev wlan0 set bitrates mcs-5 4
iw dev wlan0 set bitrates mcs-2.4 10
```
·
清除所有 `tx` 比特率和设置的东西来恢复正常：
``` shell
iw dev wlan0 set bitrates mcs-2.4
iw dev wlan0 set bitrates mcs-5
```
·
设置传输功率
可以通过使用各自的`phy`的任一设备接口名称来设置 `txpower` 。
``` shell
iw dev <devname> set txpower <auto|fixed|limit> [<tx power in mBm>]
iw phy <phyname> set txpower <auto|fixed|limit> [<tx power in mBm>]
```
·

**省电**
使能 `power save`，你可以使用：
``` shell
sudo iw dev wlan0 set power_save on
```
·
对于`mac80211`驱动程序，这意味着动态节电模式被启用。
查询当前的节电设定：
``` shell
iw dev wlan0 get power_save
```
·
**使用iw添加接口**
有几种模式可以支持。 支持的模式包括：
`monitor`
`managed [also station]`
`wds`
`mesh [also mp]`
`ibss [also adhoc]`

要添加一个 `monitor` 接口：
``` shell
iw phy phy0 interface add moni0 type monitor
``` 

### hostapd
[hostapd官方文档](http://w1.fi/hostapd/)

### wpa_supplicant

[wpa_supplicant官方文档](http://w1.fi/wpa_supplicant/)

### SDIO协议
<!-- more -->

