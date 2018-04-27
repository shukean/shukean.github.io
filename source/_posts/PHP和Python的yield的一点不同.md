---
title: PHP和Python的yield的一点不同
date: 2017-01-05 17:22:30 +0800
tags:
---

PHP中定义generator后可以直接使用，而Python中需要先初始化。

### php
```
function demo(){
    $t = yield;
    echo $t;
}

$run = demo();
$run->send(1);
```

### python
```
def demo():
    a = yield
    print(a)

run = demo()
run.send(None)
run.send(2)
```
