---
layout: article
title: 'UNRAID网卡直通'
key: 36
category: Document
tags:
- Unraid
- 网卡直通
- 软路由
---

## 前言
添加屏蔽网卡达到直通，请自行替换网卡型号。
## 编辑

MAIN——flash——Syslinux Configuration——Unraid OS

```bash
kernel /bzimage
append vfio-pci.ids=8086:1521 initrd=/bzroot
```
