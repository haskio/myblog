title: redmine的部署
tags: []
date: 2014-04-10 00:27:00
---

1、部署

两种方案

一种自行搭建 nginx+ ror +mysql

一种一键安装bitnami  有win、linux mac等一键安装。 实现均是由apache+ror 的方式

建议，如果只是为了用redmine本身的功能，还是一键安装把，后面还需要搞很多东西，节省点精力

2、插件

    1、redmine_agile  敏捷的
    www.redminecrm.com 上下载
    2、projects_tree_view  项目的树状查看
    官方wiki里找吧
    3、redmine_attach_screenshot  附件图片
    注意有一个1.18 还有一个1.0.0的，推荐用1.0.0的那个
    `</pre>

    3、主题

    使用a1，redminecrm提供的

    4、升级

    如果你是从低版本的redmine升级到高版本，比如说2.3 到2.5.需要进行数据库的升级，（注意，这时候先不要安装插件）

    <pre>`$ cd apps/redmine/htdocs

    $ bundle install --without development test postgresql sqlite

    $ ruby bin/rake redmine:plugins RAILS_ENV=production
    `</pre>

    然后插件部分：

    After copying the plugin into installdir/apps/redmine/htdocs/plugins.

    <pre>`$ cd installdir
    $ ./use_redmine
    $ cd apps/redmine/htdocs
    $ bundle install --without development test postgresql sqlite --no-deployment
    $ bundle install --without development test postgresql sqlite --deployment
    $ ruby bin/rake redmine:plugins RAILS_ENV=production
    `</pre>

    详细，请查看  http://wiki.bitnami.com/Applications/BitNami_Redmine_Stack#How_to_upgrade_Redmine.3f

    5、遇到的一些问题

    安装插件，基本上不用说什么了，按照步骤来就可以了。

    会有插件需要的gem版本跟工程的版本不一样，会有类似的问题：

    Could not find mini_portile.0.5.1 in any of the sources

    解决的办法：

    <pre>`bundle update
    #error so type command
    bundle install --no-deployment

当然，你需要先使用user_redmine,否则会提示你找不到bundle。

详细可以看这里 http://www.webhostbug.com/find-gem-version-sources/