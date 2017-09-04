# LiveSlak
Forked from Alien Bob's powerful building script for Slackware Live. Thank you, Alien !    
本套脚本 forked 自 [Alien Bob 大牛](http://www.slackware.com/%7Ealien/liveslak/), git://bear.alienbase.nl/liveslak.git


构建我自己的 Live 发行版 （基于 Slackware）。主要侧重：
  - 中文化
  - 隐私加强
    - 隐私保护和墙国特色信息/通讯自由相关的应用
    - 系统加固（包括：防火墙、文件系统加固、内核加固等……todo）


## Usage

- 下载地址：
  - Xfce（轻量版）https://mdrights.blaucloud.de/index.php/s/Nfkp9b3ROPbx9Nc
  - MATE版：https://drive.google.com/open?id=0BzDyGoE5b5SdbHpHT3FhMlllOUU   (md5sum: 51192449823679ecbe9427709b2a4795)

- 如果你是最终用户，请阅读：[LiveSlak 介绍](https://mdrights.github.io/os-observe/posts/2017/08/Liveslak-intro.html)

## Build

**如果你也想自己制作 LiveSlak 系统**   

请构建时导入这里的脚本构建的安装包：[Slackbuilds-nonprism](https://github.com/mdrights/Slackbuilds-nonprism) ，请先下载该 repo 并构建每个软件包，放置于同一个目录下（比如 $HOME/slackwareCN），LiveSlak 构建时会导入这些软件包。

    为了达到这个目的，请自行创建（或修改）本repo里的 xxx.conf & xxx.lst 配置文件（也可以用我的：mdrights{.conf, .lst}）   
    其中 `SL_REPO` 变量要指向放置你的软件包的目录（比如 $HOME/slackwareCN）

其他修改/自定义的地方就是：`make_slackware_live.conf` 
  - `SL_REPO` = 你的本地 Slackware （官方）仓库地址
  - `LIVEDE`  = 给它起个名字吧

## My modification

- #1366 & #1896: chmod a bunch of rc files as to disable them starting in booting: e.g. bluetooth,rpc,cups. If NetworkManager is installed, disabling inet1 and wireless as well.
- #2248: Enabling the addons/ & optional/ directories under XFCE mode (substituted by SLACKWARE)
- #167~: Remove some serials of Slackware repo in the tagfiles strings of MATE and CINNAMON.
- #1295: Add user account for Tor.
- Custom_config: Add my configuration files (and startup scripts) to the system.
- ....: Add Chinese (simp, trad, Cantonese) encodings options on the bootup screen.
- Add my own pkglist: mdrights{.conf,.lst} 
    - 增加了的包绝大多数为自己编译，列表在：https://github.com/mdrights/LiveSlak/blob/mdrights/pkglists/mdrights.lst
    - 您有何提议可以发issue告诉我喔～
    - 如果希望在线获得这些软件包，我可以考虑在线共享。

<hr>
构建脚本的详细介绍和使用方法请见 Alien的 [README.txt](https://github.com/mdrights/LiveSlak/blob/mdrights/README.txt)   


=========   
Copyright 2014 - 2017 Eric Hameleers, Eindhoven, NL  
Copyright 2017 MDrights (mdrights at tutanota dot de)  
All rights reserved  

只要本版权声明和许可声明出现在所有版本的本软件中，本软件即可被允许以任何目的（有偿或无偿地）使用、复制、修改和分发。  

=========

