--- 
layout: post  
title:  "Mac下安装Vim插件YouCompleteMe后 corntab编辑后保存出错"  
date:   2016-10-26 12:42:30 +0800  
description:  
---

`crontab -e`  
可以看到vim下提示YouCompleteMe插件报错,大致是python库连接无法找到的问题. 
```
YouCompleteMe unavailable: dlopen(/usr/local/Cellar/python/2.7.12/Frameworks/Python.framework/Versions/2.7/lib/python2.7/lib-dynload/_io.so, 2): Symbol not found: __PyCodecInfo_Get
IncrementalDecoder
  Referenced from: /usr/local/Cellar/python/2.7.12/Frameworks/Python.framework/Versions/2.7/lib/python2.7/lib-dynload/_io.so
  Expected in: flat namespace
 in /usr/local/Cellar/python/2.7.12/Frameworks/Python.framework/Versions/2.7/lib/python2.7/lib-dynload/_io.so
 ``` 
但我们正常打开vim却没有这个问题.  
在保存crontab时/usr/bin/vi 发现有这个提示: `crontab: "/usr/bin/vi" exited with status 1`  

原来是vim使用不一致的问题.  
将/usr/bin/vi 备份后移走, 重新建立到vim(当前使用的)的连接就没有问题了.   