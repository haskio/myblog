title: ipad1刷过精简rom 过程
tags: []
date: 2013-10-01 18:41:00
---

ipad1刷精简rom
看有人说刷了精简rom之后如同重生了一般，因此手痒也想给自己的ipad做一次升级。
下载地址
[http://bbs.weiphone.com/read-htm-tid-5183659.html](http://bbs.weiphone.com/read-htm-tid-5183659.html)
按照帖子的说法，需要先进入dfu模式，然后再通过itunes 进行恢复。这样可以绕过3194等问题。
注意要去掉之前的host 中关于gs.apple.com
实际情况是即使在dfu模式下，itunes恢复也会报3194的问题，可能是现在苹果已经关闭5.1.1 等版本的shsh验证了。

之后用了各种ireb等工具折腾半天，依旧无果。

后来用爱思助手的一键刷机，看起来蛮给力的，可以自动查询shsh（从cydia上好像），合并固件等工作。用了之后，发现一直停留在iboot这一步上。怎么折腾也无果。

太晚了就没怎么折腾。
第二天看到有帖子说，如果是用台式机，查前面的口可能就会这样的问题，导致软件不能自动进入ref模式，所以超时出错。于是把线插到后面的口上。
又实验了一边各种ireb、红雪dfu等方式，依旧提示 3194问题，不给力。最后用爱思助手，一次搞定。

刷完新系统，先运行Release Me Now 3.0，作者说要重启，一定要重启，那咱们就重启吧。
重启完进cydia，
添加源什么的就不用说了
weiphone源。 apt.weiphone.com.
178：[http://apt.178.com](http://apt.178.com)
百度输入法源，源地址为：[http://mi.baidu.com](http://mi.baidu.com) 设置输入法
安装iFile
安装AppSync for ios5+ ，感兴趣的可以装一个虚拟内存，据说可以实现玩植物大战僵尸2不闪退。非常犀利。
先从
rom说明和下载：
[http://bbs.weiphone.com/read-htm-tid-5183659.html](http://bbs.weiphone.com/read-htm-tid-5183659.html)
其他一些问题的解决方案：
[http://bbs.weiphone.com/read-htm-tid-5366158.html](http://bbs.weiphone.com/read-htm-tid-5366158.html)
装个虚拟内存吧
[http://bbs.weiphone.com/read-htm-tid-3872615-page-1.html](http://bbs.weiphone.com/read-htm-tid-3872615-page-1.html)