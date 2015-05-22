title: 终于搞定 iomega ix2-dl的开机自启了
tags: []
date: 2013-10-15 18:28:00
---

总的来说，还是在/etc/rc.local 里，其他的方式都不管用。
我的是增加了

    sleep 60

    aria2c

    alias rm='rm -i'

    alias cp='cp -i'

    alias mv='mv -i'

    alias ll='ls -l --color=tty'

    alias lla='ls -la --color=tty'

    /opt/bin/aria2c --save-session=/mnt/pools/A/A1/Downloads/aria2/aria2.session --enable-rpc --rpc-listen-all=true --rpc-listen-port=6800 --rpc-allow-origin-all --dir=/mnt/pools/A/A1/Movies --file-allocation=none -s 5 -j 3 -x 5 -c -D

参考的如下：[http://www.xxb.me/2013/04/iomega_ix2-dl_rc-local_path/](http://www.xxb.me/2013/04/iomega_ix2-dl_rc-local_path/)