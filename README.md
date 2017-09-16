# LiveSlak

> Forked from Alien Bob's powerful building script for Slackware Live. Thank you, Alien !    
> 本套脚本 forked 自 [Alien Bob 大牛](http://www.slackware.com/%7Ealien/liveslak/), git://bear.alienbase.nl/liveslak.git


构建我自己的 Live 发行版 （基于 Slackware）。主要侧重：
  - 中文化
  - 隐私加强
    - 隐私保护和墙国特色信息/通讯自由相关的应用
    - 系统加固（包括：防火墙、文件系统加固、内核加固等……todo）

## Download

- 下载地址 _（可能会因更新而变动）_：
  - https://mdrights.blaucloud.de/index.php/s/03oc1NgbKoI9RCR    
  - 包含：
    - Xfce 版（0916; 最小安装版）
    - MATE 版 ( 0910)

_最后更新：2017.09.16 22:30_    

<hr>

## Usage

- 如果你是**最终用户**，请阅读：[LiveSlak 最终用户介绍](https://mdrights.github.io/os-observe/posts/2017/08/Liveslak-intro.html)

## Build

**如果你也想自己制作 LiveSlak 系统**   

请构建时导入这里的脚本构建的安装包：[Slackbuilds-nonprism](https://github.com/mdrights/Slackbuilds-nonprism) ，请先下载该 repo 并构建每个软件包，放置于同一个目录下（比如 $HOME/slackwareCN），LiveSlak 构建时会导入这些软件包。

    为了达到这个目的，请自行创建（或修改）本repo里的 xxx.conf & xxx.lst 配置文件（也可以用我的：mdrights{.conf, .lst}）   
    其中 `SL_REPO` 变量要指向放置你的软件包的目录（比如 $HOME/slackwareCN）

其他修改/自定义的地方就是：`make_slackware_live.conf` 
  - `SL_REPO` = 你的本地 Slackware （官方）仓库地址
  - `LIVEDE`  = 给它起个名字吧

## My modification

- #519: Change the default locale in the first option on the syslinux boot menu, to zh; and delete the option/submenus for non-US keyboard.
- #1366 & #1896: chmod a bunch of rc files as to disable them starting in booting: e.g. bluetooth,rpc,cups. If NetworkManager is installed, disabling inet1 and wireless as well.
- #2248: Enabling the addons/ & optional/ directories under XFCE mode (substituted by SLACKWARE)
- #167+: Remove some serials of Slackware repo in the tagfiles strings of MATE and CINNAMON.
- #1295: Add user account for Tor.
- #1591: Disable most of the KDE4 configuration (for X system) when not building for KDE4 type.
- Custom_config: Add my configuration files to the system, which can be put under such paradigm:    
  - skel/skel*.txz : any files except skel-xfce.txz in it will be put to $HOME under **every desktopType except XFCE** which only parse skel-xfce.txz;
  - rootcopy/ : now we can have **etc-x.txz** & **opt-x.txz** that can be parsed to /etc and /opt respectively.
- ....: Add Chinese (simp, trad, Cantonese) encodings options on the bootup screen.
- Add my own pkglist: mdrights{.conf,.lst} 
    - 增加了的包绝大多数为自己编译，列表在：https://github.com/mdrights/LiveSlak/blob/mdrights/pkglists/mdrights.lst
    - 您有何提议可以发issue告诉我喔～
    - 如果希望在线获得这些软件包，我可以考虑在线共享。

## Change Log

- 2017.09.16	增加了 Jitsi；修正 Tor-hardened的錯誤（去掉 chroot功能；保留了 Tor 的 Stream Isolation 配置（可用）；增加了 iptables防火牆規則，可以讓**本地**所有流量強制走 socks代理和/或 Tor（但非透明代理）；還增加了 iptables規則可讓本系統變身 “洋蔥” 網關，連接並流入本系統的機器流量都被走Tor隧道（透明代理））。
- 2017.09.09	增加了一些与数据保护相关的工具： `wipe`, `secure-delete`, `testdisk`; 增加了文本编辑器：`Ted`, `docx2txt`。
- 2017.09.07	去掉了一些不必要的配置文件；修正桌面快捷方式的错误并添加了一个；在XFCE版作为超级轻量版舍去一些因缺少依赖而无法运行的包（可待在MATE版提供）。
- 2017.09.06	添加了两个桌面快捷方式：防火墙和无线网络连接。
- 2017.09.05	Discard firewall startup script; All things work now!
- 2017.09.04	First beta point release: firewall startup added to rc.local/rc.local_shutdown (but found conflicted with xdm)
- 2017.09.03	First beta release:	Tor user account added; Firewall rc script added; ShadowsockR added in /opt.
- 2017.08.27	First beta pre-release: basic feature done (but Tor un-functionable)

## TODO

- Firefox and Icecat user config files (user.js, extensions.ini) are not able to install to user's directory, since the FF/Icecat user `.mozilla` directory has not been made until FF/icecat first start; and the profile directory inside `.mozilla` is a random number. However this does not affect FF's extension installation (but icecat will).
- It seems xdm cannot start DE while Iptables autostart during the boot.
- It seems that the UEFI grub won't show menu when it is initiated, with only the `boot:` prompt. Nothing has been found to figure this out yet (neither not the problem of grub fonts, nor the problem of the minimal installation under XFCE...)
- Virtualbox-guest-addons is still not yet been successfully built for my -current environment...


## Acknowledgement

- 非常感謝 TG上的 Aaron Nexus 給予的測試;-)  Thanks a million for Aaron Nexus (on Telegram) for tireless testing :)

<hr>
构建脚本的详细介绍和使用方法请见 Alien的 [README.txt](https://github.com/mdrights/LiveSlak/blob/mdrights/README.txt)   

**交流反饋**：這裏發issue，或 IRC/Riot 頻道：#digitalrightscn ; 或 TG: https://t.me/joinchat/EMyvPA4M5YBESP74ID9qIA    

=========   
Copyright 2014 - 2017 Eric Hameleers, Eindhoven, NL  
Copyright 2017 MDrights (mdrights at tutanota dot de)  
All rights reserved  

只要本版权声明和许可声明出现在所有版本的本软件中，本软件即可被允许以任何目的（有偿或无偿地）使用、复制、修改和分发。  

=========

