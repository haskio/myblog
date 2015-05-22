title: centos6.3 安装zpanel、中文补丁以及文件管理器
tags: []
date: 2014-01-26 17:30:00
---

centos6.3 安装zpanel、中文补丁以及文件管理器

使用hi-vps.com kvm，安装的是centos 6.3 x64 版

##安装zpanel

###1、下载

64 Bit 安装

wget http://www.zvps.co.uk/sites/default/files/downloads/centos-6-3/package/installer-x86_64-install.sh.x.tar.gz

32 bit 安装

wget http://www.zvps.co.uk/sites/default/files/downloads/centos-6-3/package/installer-x86-install.sh.x.tar.gz

###2、解压

64 Bit Installer

tar -xf installer-x86_64-install.sh.x.tar.gz

32 Bit Installer

tar -xf installer-x86-install.sh.x.tar.gz

注意，很多地方都会在这里新建目录，其实不新建也可以

###3、添加可运行权限

64 Bit Installer

chmod +x installer-x86_64-install.sh.x

32 Bit Installer

chmod +x installer-x86-install.sh.x

###4、安装环境

Install pre-required packages:

yum install ld-linux.so.2 curl

###5、执行安装

64 Bit Installer

./installer-x86_64-install.sh.x

32 Bit Installer

./installer-x86-install.sh.x

###6、安装过程

y 之后一路回车，直到设置mysql密码 ，然后是域名，可以随意写，到时候登录用ip就可以。

最后提示你：ZPanel will now install， are you sure （y/n/q）？ 输入：y

然后返回安装信息，用户名密码等，如果你忘了，可以查看

##安装中文支持

教程来自

http://www.hostoc.com/thread-4155-1-1.html

###1、安装模块文件

使用ssh登录服务器执行以下命令

zppy repo add zpanel-packages.sammottley.co.uk

zppy update

成功会显示以下信息

pdating package list..

Connecting to packages.zpanelcp.com

Getting list from packages.zpanelcp.com

Failed to contact the URL 'packages.zpanelcp.com'

Connecting to zpanel-packages.sammottley.co.uk

Getting list from zpanel-packages.sammottley.co.uk

Local package cache is now up-to-date!

然后再执行

zppy install ZXTS   （注意ZXTS为大写）

###2、设置模块可用

登录zpanel 中admin 组中mod manger 的，找到ZXTS 设置为admin 可用

###3、启动ZXTS

在功能面板中点击ZXTS启动， 在语言选择中选择Mandarin 语言进行安装，不用管进度。

###4、启用语言

到用户 My Account 中 Choose Language 为 Mandarin。 update 后生效。

##安装在线文件管理器

zpanel 不支持在线文件管理，因此很不方便，我们添加一个模块来支持

教程来源http://www.hostoc.com/thread-4156-1-1.html

###1、安装模块

zppy repo add zppy.vjdev.co.uk

zppy update

zppy install ajaxplorer

###2、启用

登录zpanel 中admin 组中mod manger 的，找到ajaxplorer ，设置为所有用户可用。

大体上的轮廓折腾完了，但是如何让zpanel 支持 zend 还没有什么好的办法。