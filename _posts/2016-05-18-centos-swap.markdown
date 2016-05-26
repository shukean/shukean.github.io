---
title:  "Centos swap 命令"
date:   2016-05-23 10:18:00
description: Thriller Comedy Horror
---

1. 查看swap空间大小
{% highlight sh %}
# free -m
{% endhighlight %}
看到 swap： 该行的信息

2. 查看swap的设置的文件
{% highlight sh %}
＃swapon -s
{% endhighlight %}

3. 删除swap的空间
{% highlight sh %}
＃swapoff  swap_path
{% endhighlight %}

4. 设置swap
{% highlight sh%}
# dd if=/dev/zero of=swap_path bs=1024 count=2048000      '添加交换文件并设置其大小为2G
# mkswap swap_path   '创建（设置）交换空间，使用命令mkswap
# swapon swap_path   '启动新增加的2G的交换空间，使用命令swapon 
{% endhighlight %}
确认新增加的2G交换空间已经生效，使用命令free -m

