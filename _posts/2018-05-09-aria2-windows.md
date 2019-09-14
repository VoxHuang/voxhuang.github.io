---
layout: article
title: 'aria2 Windows懒人配置教程'
key: 13
category: Document
tags:
- Aria2
- 下载
---

Aria2是一个多平台轻量级，支持 HTTP、FTP、BitTorrent 等多协议、多来源的命令行下载工具。Aria2 可以从多个来源、多个协议下载资源，最大的程度上利用了你的带宽。Aria2 有着非常小的资源占用，在关闭磁盘缓存的情况下，物理内存占用通常为 4M（正常 HTTP/FTP 下载的情况下），BitTorrent 下载每秒2.8M/S的情况下，CPU 占有率约为 6%。Aria2 支持 JSON-RPC 和 XML-RPC 接口远程调用。

很多人在 Windows 可能用过 Internet Download Manager，是很好用的多线程下载工具。Aria2 跟 IDM 类似，不仅可以多线程下载，还可以通过多来源进行下载，简单的说就是从多个镜像服务器同时下载一个文件，Aria2 还支持 BT 协议，弥补了 IDM 只支持 HTTP 和 FTP 的痛点。

不过，Aria2是命令行工具，普通用户使用起来有难度。

## 准备工作

1：在 [Aria2官方原版](http://aria2.github.io/) 或 [Aria2 with Open SSL](http://github.com/q3aql/aria2-static-builds/) 下载对应平台的核心包

2：将下载的压缩包中的 aria2c 文件解压后放到 Aria2 文件夹中


## 配置文件下载

### [Github](https://github.com/VoxHuang/Aria2-Android-and-Windows-shell)

```bash
https://github.com/VoxHuang/Aria2-Android-and-Windows-shell
```

## 安装运行

1：将该(Aria2)文件夹放到任意非系统目录下

2：重复执行 aria2.wsf 即可启动或关闭Aria2

## 管理使用

1：浏览器打开 https://voxhuang.github.io/aria2 进行查看和管理

```
https://voxhuang.github.io/aria2 
```

2：默认JSON-RPC为 http://localhost:6800/jsonrpc  密钥：voxhuang.com

3：默认下载目录自行更改

## 注意事项

1：在安装之前，您可以随意移动或修改文件夹名称，但是在安装之后相关配置文件中的路径便会成为固定值，这时请不要再随意移动或更改其文件夹名称

2：如果您使用的是精简版系统，并且 VBScript 运行所需的系统文件缺失，您将无法使用这些脚本，但您可以使用VbsEdit软件将其转换为exe程序来使用

3: 本脚本已做对带空格路径的处理，但是如果在aria2.conf中填写并启用了含中文路径的参数，Aria2将可能不能启动或工作异常，这个问题与本脚本无关

## 可选内容

1：optional文件夹下的内容为可选项，使用前需要将文件移动至 aria2.wsf 同目录下

2：如果需要开机自启可以使用 daemon.wsf，请注意这个脚本不是自动添加到系统启动项，您可以手动为其创建快捷方式并放到[开始菜单中的启动目录](http://voxhuang.com/document/2018/05/09/win10-Startup.html)

-->daemon.wsf 有守护进程的作用，脚本默认以 每60秒间隔 检查Aria2的存活状态，如果Aria2异常关闭，则自动重启Aria2
-->daemon.wsf 执行后可以在任务管理器中进行关闭，如需卸载Aria2，请先关闭程序或禁用脚本自启后重启设备，然后删除所有Aria2相关文件即可
-->daemon.wsf 执行后无内容输出，切勿多次执行，并请注意 sleep 时间修改过短将可能导致设备卡顿或增加功耗
-->daemon.wsf 的监控功能在不同系统环境下并不一定总是有效，实际效果请自行测试

3：aconf.bat 用于简化配置文件，首次运行完成后原文件会被重命名为 aria2.conf.backup，再次运行会从aria2.conf.backup重新生成aria2.conf

4：error.bat 和 complete.bat 用于aria2.conf中的【 任务状态相关 】
-->error.bat 用于在下载出现错误时，通过error.wsf播放音频文件error.wav，同时使用iexplorer打开WebUI，但是如果iexplorer正在运行则不会执行操作，避免在出现多个错误时重复运行
-->complete.bat 用于在下载全部完成时，通过complete.wsf播放音频文件complete.wav，但是如果在程序运行中通过WebUI临时更改下载路径，本脚本将不能正确工作
-->error.bat，complete.bat，error.wsf，complete.wsf 默认须在同一目录下
-->error.wav，complete.wav 默认须放于脚本同目录下

5：aria2.conf中配置vbs/wsf脚本将不能被执行，cmd/bat文件只能和核心同目录，com/exe程序可以被指定路径

## 配置文件

1：默认配置文件为 aria2.conf，在首次运行aria2.sh并且成功时生成在当前脚本目录下

2：井号开头的参数将使用默认值，请根据相应参数说明进行修改，具体可用参数视核心版本而定

3：更多信息请查阅官方在线文档 [查阅官方在线文档](https://aria2.github.io/manual/en/html/aria2c.html)

## 网页界面

### [网页界面](https://voxhuang.github.io/aria2)

```bash
https://voxhuang.github.io/aria2
```

## 参考文贴

参考原帖地址：https://www.52pojie.cn/thread-643693-1-1.html
