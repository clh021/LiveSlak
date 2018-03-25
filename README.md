# LiveSlak

> Forked from Alien Bob's powerful building script for Slackware Live. Thank you, Alien !    
> 本套脚本 forked 自 [Alien Bob 大牛](http://www.slackware.com/%7Ealien/liveslak/), git://bear.alienbase.nl/liveslak.git

_最后更新：2018.02.19_    

构建我自己的 Live 发行版 （基于 Slackware）。主要侧重：
  - 中文化
  - 隐私加强
    - 隐私保护和墙国特色信息/通讯自由相关的应用
    - 系统加固（包括：防火墙、文件系统加固等……）

## Download

- 下载地址 _（可能会因更新而变动）_：
	- https://sourceforge.net/projects/liveslak-atgfw/files/iso/
  - 自 2018.02 (新版本号，代号：ATGFW，声援甄江华并支持他和伙伴的网站) 开始只发布带 XFCE桌面的完整版（大小：1988100096 B）
	- md5sum: 39db36c7e4895c5dc18eb6b30a3229ec


<hr>

## Usage

- 如果你是**最终用户**，请阅读：    
	- [LiveSlak 最终用户介绍](https://mdrights.github.io/os-observe/Liveslak-intro/)
	- [《用户手册》](https://github.com/mdrights/LiveSlak/blob/mdrights/LiveSlak-Users-Guide.md)

## Device Requirements

- 您的机器必须是 x86_64位的啦；
- 需要至少 2G 内存；
- 这意味着如果你在虚拟机里运行，请为其设置足够的内存，而虚拟机的宿主机至少要有 4G 物理内存。
- 经测试，有的电脑只有 (U)EFI（主板启动固件）, Slackware 的 bootloader (syslinux + grub2) 可能无法广泛地支持所有 UEFI。如果遇到机器无法识别本系统的U盘——这情况请选择传统 BIOS 或带 CSM 的 EFI的电脑使用，或者在虚拟机里使用（并请告诉我 Orz）。



## Change Log

- 2018.02.19	大更新：内核 4.9.81（CPU两漏洞补丁上游已完善）；Tor浏览器-> 7.5，Shadowsocks-libev -> 3.1.3, v2ray -> 3.9, Riot.im -> 0.13.5, Telegram 1.2.6, etc.; 抛弃cinnamon，拥抱xfce，用了自定义的 pkglist -> xfce 安装了完整的 slackware官方包了；重整了xfce菜单，重要软件的菜单项添加中文，并归到独自的子菜单：「翻越长城」和「数据保护」； 自制的 ATGFW 桌面（声援甄江华并支持他和伙伴的网站）
- 2018.01.14	use my self-built kernel: 4.9.76 which was directly from kernel.org as the patched and updated version in response to Meltdown and Spectre. Updated Tor (0.3.2.9) 
- 2017.12.08	新增：Shadowsocks（原版，2.9.1）；更新：v2ray（3.0.1），Tor（0.3.2.6-alpha）；系统官方更新（内核 4.9.66）  
- 2017.11.10	更新 Tor (3.2.3-alpha), Tor Browser(7.0.9), Icecat(52.3.0), Icecat-hardened（安装后即可用插件了：Noscript, HTTPSeverywhere, Privacy Badger，和中文语言包）; XFCE版去除了 GIMP（减轻重量），CINNAMON版增加了 youtube-dl（油管下载神器）；官方更新跟进（eg -> Firefox 56).  
- 2017.10.28	跟进官方10.20更新（包括wpa_supplicant安全更新）；新增 Riot 客户端，qTox 客户端（p2p分布式通讯应用）；	
- 2017.10.07	暂时**移除**蓝灯（因为发现其在用阿里云的海外服务器，可信度大大降低）；新增 `v2ray`；修复ssr/ss-libev脚本的bugs。  
- 2017.10.04	新增了 Tor-messenger 和 Lantern蓝灯（注：蓝灯并非在所有地区都有效）。
- 2017.10.03	加入了藏文（bo_IN, bo_CN）和维吾尔文（ug_CN）的显示支持（注：目前来说维吾尔文支持较好，而有些应用/桌面没有藏文的翻译项目，还需要更多藏语使用者对各应用和桌面（如 XFCE）提供翻译。）  
- 2017.09.30	更新一些自添加的软件：Tor-nonprism（修复防火墙规则）；Icecat-hardened（用户配置改为无痕浏览和默认socks5代理（不过启动两次浏览器才生效））；升级 shadowsocks-libev至3.1.0；新增 Signal-Desktop；Libreoffice 新增中文包，即界面默认为中文了；新增ssr脚本和 ss-redir透明代理脚本（详情见《用户手册》）。
- 2017.09.24	上游更新（包括添加了 python 3.6）
- 2017.09.17	上游系統更新（見[repo](https://mirrors.slackware.com/slackware/slackware64-current/ChangeLog.txt)）；包括內核升至4.9.50，修復包括BlueBorne藍牙模塊的漏洞。
- 2017.09.16	增加了 Jitsi；修正 Tor-hardened的錯誤（去掉 chroot功能；保留了 Tor 的 Stream Isolation 配置（可用）；增加了 iptables防火牆規則，可以讓**本地**所有DNS流量強制走 Tor，避免了DNS泄漏（透明代理）；還增加了 iptables規則可讓本系統變身 “洋蔥” 網關，連接並流入本系統的機器的所有流量都走Tor隧道（透明代理））。
- 2017.09.09	增加了一些与数据保护相关的工具： `wipe`, `secure-delete`, `testdisk`; 增加了文本编辑器：`Ted`, `docx2txt`。
- 2017.09.07	去掉了一些不必要的配置文件；修正桌面快捷方式的错误并添加了一个；在XFCE版作为超级轻量版舍去一些因缺少依赖而无法运行的包（可待在MATE版提供）。
- 2017.09.06	添加了两个桌面快捷方式：防火墙和无线网络连接。
- 2017.09.05	Discard firewall startup script; All things work now!
- 2017.09.04	First beta point release: firewall startup added to rc.local/rc.local_shutdown (but found conflicted with xdm)
- 2017.09.03	First beta release:	Tor user account added; Firewall rc script added; ShadowsockR added in /opt.
- 2017.08.27	First beta pre-release: basic feature done (but Tor un-functionable)

## My modification

- 519: Change the default locale in the first option on the syslinux boot menu, to zh; and delete the option/submenus for non-US keyboard.
- 1366 & 1896: chmod a bunch of rc files as to disable them starting in booting: e.g. bluetooth,rpc,cups. If NetworkManager is installed, disabling inet1 and wireless as well.
- 2248: Enabling the addons/ & optional/ directories under XFCE mode (substituted by SLACKWARE)
- 167+: Remove some serials of Slackware repo in the tagfiles strings of MATE and CINNAMON.
- 1295: Add user account for Tor.
- 1591: Disable most of the KDE4 configuration (for X system) when not building for KDE4 type.
- Custom_config: Add my configuration files to the system, which can be put under such paradigm:    
  - skel/skel\*.txz : any files except skel-xfce.txz in it will be put to $HOME under **every desktopType except XFCE** which only parse skel-xfce.txz;
  - rootcopy/ : now we can have **etc-x.txz** & **opt-x.txz** that can be parsed to /etc and /opt respectively. (otherwise seems rootcopy/ doesn't work)  
- ....: Add Chinese (simp, trad, Cantonese) encodings options on the bootup screen.
- Add my own pkglist: mdrights{.conf,.lst} 
    - 增加了的包绝大多数为自己编译，列表在：https://github.com/mdrights/LiveSlak/blob/mdrights/pkglists/mdrights.lst
    - 您有何提议可以发issue告诉我喔～
    - 如果希望在线获得这些软件包，我可以考虑在线共享（但仍建议你自己编译）。
- Hard-coded $KVER in line 2101, in order to let my sel-built kernel work. Also, my self-built kernel packages replaced with the same-name ones in `Slackware-repo` in my machine. The result seems to show that the kernel-generic was the one it used in place (I replaced both generic and huge packages with the same kernel built based on huge-4.9.66). I didn't build kernel-headers. And it was only successful that the kernel-modules package installed while the modules were installed via the kernel-[generic|huge] packages already. So I made kernel-modules package as a meta-package (empty but only a text in /lib/modules ). There's no need to touch tagfiles and pkglist/min.lst.   

## TODO

- Firefox and Icecat user config files (user.js, extensions.ini) are not able to install to user's directory, since the FF/Icecat user `.mozilla` directory has not been made until FF/icecat first start; and the profile directory inside `.mozilla` is a random number. However this does not affect FF's extension installation (but icecat will).
- It seems xdm cannot start DE while Iptables autostart during the boot.
- It seems that the UEFI grub won't show menu when it is initiated, with only the `boot:` prompt. Nothing has been found to figure this out yet (neither not the problem of grub fonts, nor the problem of the minimal installation under XFCE...)
- Virtualbox-guest-addons is still not yet been successfully built for my -current environment...

## Build

**如果你也想自己制作 LiveSlak 系统**   

可以参考这里的打包脚本制作Slackware安装包（打包方法见每个脚本里的README）：

- [Slackbuilds-nonprism](https://github.com/mdrights/Slackbuilds-nonprism) 

- 还有更多： [Slackwarecn-slackbuilds](https://github.com/slackwarecn-slackbuilds)

把用以上打包脚本构建的包（tgz 或 txz）放置于同一个目录下（比如 $HOME/slackwareCN），LiveSlak 构建时会导入这些软件包。

    为了达到这个目的，请自行创建（或修改）本repo里的 xxx.conf & xxx.lst 配置文件（也可以用我的：mdrights{.conf, .lst}）   
    其中 `SL_REPO` 变量要指向放置你的软件包的目录（比如 $HOME/slackwareCN）

其他修改/自定义的地方就是：`make_slackware_live.conf` 
  - `SL_REPO` = 你的本地 Slackware （官方）仓库地址
  - `LIVEDE`  = 给它起个名字吧



## Acknowledgement

- 非常感謝 TG上的 Aaron Nexus 給予的測試;-)  Thanks a million for Aaron Nexus (on Telegram) for tireless testing :)

<hr>
构建脚本的详细介绍和使用方法请见 Alien的 [README.txt](https://github.com/mdrights/LiveSlak/blob/mdrights/README.txt)   

**交流反饋**：這裏發issue，或 IRC/Matrix: #DigitalrightsCN; TG頻道：https://t.me/liveslak ; 或 群组: https://t.me/joinchat/EMyvPA4M5YBESP74ID9qIA    



==============================================================================   
Copyright 2014 - 2017 Eric Hameleers, Eindhoven, NL  
Copyright 2017 MDrights (mdrights at tutanota dot de)  
All rights reserved  

只要本版权声明和许可声明出现在所有版本的本软件中，本软件即可被允许以任何目的（有偿或无偿地）使用、复制、修改和分发。  

    Permission to use, copy, modify, and distribute this software for
#   any purpose with or without fee is hereby granted, provided that
#   the above copyright notice and this permission notice appear in all
#   copies.
#
#   THIS SOFTWARE IS PROVIDED ``AS IS'' AND ANY EXPRESSED OR IMPLIED
#   WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF
#   MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED.
#   IN NO EVENT SHALL THE AUTHORS AND COPYRIGHT HOLDERS AND THEIR
#   CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
#   SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
#   LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF
#   USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND
#   ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
#   OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT
#   OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF
#   SUCH DAMAGE.
# -----------------------------------------------------------------------------

