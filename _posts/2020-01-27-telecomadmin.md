---
layout: article
title: '天翼网关获取超级密码'
key: 32
category: Document
tags:
- 宽带
- 天翼网关
- VoxHuang
---

## 前言
获取天翼网关超级管理密码
## 命令

烽火光猫

```bash
http://192.168.1.1:8080/cgi-bin/baseinfoSet.cgi
```

Python Code

```bash
list=[120,105,112,105,103,115,113,101,104,113,109,114,55,51,50,51,48,54,57,48]
result=[]
for i in list:
    if i > 57:
        i-=4
    result.append(chr(i))
print ''.join(result)
```

[在线Python编程](http://www.pythontip.com/coding/run)

```bash
http://www.pythontip.com/coding/run
```

