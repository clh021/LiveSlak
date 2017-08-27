# LiveSlak
Forked from Alien Bob's powerful building script for Slackware Live. Thank you, Alien !    
本套脚本 forked 自 [Alien Bob 大牛](http://www.slackware.com/%7Ealien/liveslak/), git://bear.alienbase.nl/liveslak.git


构建我自己的 Live 发行版 （基于 Slackware）。主要侧重：
  - 中文化
  - 隐私加强
    - 隐私和安全相关的应用
    - 系统加固（TODO）

## Usage

**如果你也想自己制作 LiveSlak 系统**   

请构建时导入这里的脚本构建的安装包：[Slackbuilds-nonprism](https://github.com/mdrights/Slackbuilds-nonprism) ，请先下载该 repo 并构建每个软件包，放置于同一个目录下（比如 $HOME/slackwareCN），LiveSlak 构建时会导入这些软件包。

    为了达到这个目的，请自行创建（或修改）本repo里的 xxx.conf & xxx.lst 配置文件（也可以用我的：mdrights{.conf, .lst}）   
    其中 `SL_REPO` 变量要指向放置你的软件包的目录（比如 $HOME/slackwareCN）

其他修改/自定义的地方就是：`make_slackware_live.conf` 
  - `SL_REPO` = 你的本地 Slackware （官方）仓库地址
  - `LIVEDE`  = 给它起个名字吧


<hr>
_构建脚本的详细介绍和使用方法请见 Alien的 [README.txt](https://github.com/mdrights/LiveSlak/blob/mdrights/README.txt)_
