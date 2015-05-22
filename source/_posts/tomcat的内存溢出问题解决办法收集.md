title: tomcat的内存溢出问题解决办法收集
tags: []
date: 2014-03-14 21:03:00
---

项目中，使用的是j2ee的框架，容器用的是tomcat 。虽然说机器很给力，都是4核、8核的cpu以及64g的内存，但是在运行过程中，总是产生这样那样的问题，研究了半天，归纳为几类，其中占比较多是tomcat的内存溢出问题，尤其我不是做java开发以及运维的，只能查询网上的资料。以下是收集的内容。

##讨论帖子1

http://www.iteye.com/topic/80620

###解决方案

1/ 增加p区的大小

gc 启动参数里 增加-XX:MaxPermSize=256m

2/ 换jdk

Jrockit

3/

另外如果使用CMS（ConcMarkSweep GC）算法的话，开了-XX:+UseConcMarkSweepGC标志，默认情况下就是不会扫描permanent generation的，需要同时打开下面两个标志位才能让CMS GC扫描permanent generation。

-XX:+CMSPermGenSweepingEnabled

-XX:+CMSClassUnloadingEnabled

P.S. 只针对SUN的JVM有效。

4/

”可设置-XX:+CMSClassUnloadingEnabled -XX:+CMSPermGenSweepingEnabled，使CMS收集持久代的类，而不是fullgc，netbeans5.5 performance文档的推荐。“

##讨论帖子2

###java.lang.OutOfMemoryError: Java heap space

Heap size 设置

修改TOMCAT_HOME/bin/catalina.sh

在“echo &quot;Using CATALINA_BASE:   $CATALINA_BASE&quot;”上面加入以下行：

JAVA_OPTS=&quot;-server -Xms800m -Xmx800m   -XX:MaxNewSize=256m&quot;

##讨论内容3

###java.lang.OutOfMemoryError: PermGen space及其解决方法

http://www.wujianrong.com/archives/2006/12/javalangoutofmemoryerror_permg.html

##gc回收机制

http://blog.csdn.net/calvinxiu/article/details/1614473

##jvm配置大全

http://ggmm.blog.sohu.com/117545379.html

##Java中OutOfMemoryError与unable to create new native thread(JVM创建大量线程)的关系

http://hi.baidu.com/hexiong/item/037488116cefd90a8ebde4b1