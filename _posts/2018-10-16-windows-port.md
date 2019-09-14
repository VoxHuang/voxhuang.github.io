---
layout: article
title: '查看windows 端口占用情况'
key: 23
category: Document
tags:
- 端口
- windows
- CMD

---

## 查看windows 端口占用情况

查看windows 端口占用情况，例如端口1080,CMD运行命令


```
netstat -aon|findstr 1080
```

