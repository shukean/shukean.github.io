---
title:  "Safari强制切换http到https的问题"
date:   2016-07-12 12:33:00 +0800
description: 
---


实验时,将baidu.com host localhost, 再safari下无法访问. 提示 safari error can't establish secure connection
Google后发现有类似的问题:
http://apple.stackexchange.com/questions/215077/safari-redirecting-http-to-non-existent-https


~/Library/Cookies/HSTS.plist 删除没用,因为会自动创建. 可以清空后,设置自读即可.
清空~/Library/Cookies/ 下  *cookies 的文件.
重启safari.
