title: android 修改默认接入点 cmcc
tags: 接入点
categories: 记录
date: 2013-09-29 18:40:00
---

删除Wifi的CMCC和CMCC-edu默认信任接入点.
先获取Root权限， re管理器进入/etc/wifi/wpa_supplicant.conf，(用编辑器打开)
删除（删除前建议做好备份，就是将wpa_supplicant.conf文件复制一份，万一修改错误还可以恢复）以下代码：
network={ssid=“cmcc” key-mgmt=none priorty=2 }
network={ssid=“cmcc-edu” key-mgmt=none priorty=1 }
再删除/DATA/MISC/WIFI里的wpa_supplicant.conf里的同样ssid="CMCC"和ssid="CMCC-edu"字段
network={ssid=“cmcc” ...... }
network={ssid=“cmcc-edu” ...... }
保存并退出，重启手机后你会发现虽然还有默认信息接入点，但它不会自动接入CMCC或CMCC-edu了。