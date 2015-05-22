title: sublime text 怎么在新标签中打开文件?
tags: []
date: 2014-04-28 23:52:00
---

在 use 配置里 增加：

open_files_in_new_window并改为false，像下面这样：

`&quot;openfilesinnewwindow&quot;: false，`

结果又出现保持问题：

Error trying to parse settings

搜索后发现，sublime text 的配置，最后一行是不可以加逗号的。

如果你是放在最后，需要把原来上面的那行加上逗号“,”，本行去掉。

在这里，有汉化包可以用：

http://www.sublimetextcn.com/

在使用了汉化包之后，又出现光标又粗又大的问题。。

结果是需要在设置里设置光标的像素，接着增加设置吧，需要设置的内容如下：

*   caret_extra_top 超出光标上方的额外距离
*   caret_extra_bottom&nbsp;超出光标下方的额外距离
*   caret_extra_width&nbsp;超出光标宽度

增加配置代码：

`<p>“caretextratop”: 1,

“caretextrabottom”: 1,

“caretextrawidth”: 1
`</p>

解决方案来自：

http://www.kankanews.com/ICkengine/archives/106640.shtml