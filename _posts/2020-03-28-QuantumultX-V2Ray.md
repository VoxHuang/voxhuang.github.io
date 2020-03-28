---

layout: article
title: 'Quantumult X 某自建科学配置添加方式'
key: 40
category: Document
tags:
- Quantumult X
- 不可描述
- VPS
---

## 前言
Quantumult X 某自建科学配置添加方式
## 步骤

配置文件，编辑，【server-local】下添加

```bash
vmess=IP:443, method=aes-128-gcm, password=xxxxxxx-xxxx-xxxx-xxxx-xxxx, obfs-host=IP, obfs=wss, obfs-uri=/路径 , tls-verification=true,fast-open=false, udp-relay=false, tag=备注
```
