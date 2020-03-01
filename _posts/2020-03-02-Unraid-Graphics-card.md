---
layout: article
title: 'UNRAID调用直通Intel核显并开机自启动'
key: 33
category: Document
tags:
- Unraid
- 直通
- 核显
---

## 前言
UNRAID调用直通Intel核显并开机自启动，及docker的应用。
## 命令

SSH执行命令查看核显状态

```bash
ls /dev/dri
```

开启核显命令

```bash
modprobe i915
```

设置开机自启动

```bash
cd /boot/config
```

编辑go文件

```bash
vi go
```

添加开机自启动命令，按i编辑，&后面回车换行输入

```bash
modprobe i915
```

按esc键退出修改，:wq保存

```bash
:wq
```

## 应用

Extra Parameters栏输入

```bash
--device=/dev/dri
```

或直接添加设备映射

```bash
/dev/dri
```

