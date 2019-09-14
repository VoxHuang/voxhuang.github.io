---
layout: article
title: 'aria2安卓懒人配置教程'
key: 12
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

3：安装一款可以执行脚本的文件管理器如:RootEplore文件管理器 或 MT文件管理器

## 配置文件下载

### [Github](https://github.com/VoxHuang/Aria2-Android-and-Windows-shell)

```bash
https://github.com/VoxHuang/Aria2-Android-and-Windows-shell
```

## 安装运行

#### 未Root用户：
1：使用文件管理器将 Aria2 文件夹放到内置存储任意目录下，如根目录：

```
/sdcard
```

2：打开上述文件管理器点击脚本执行aria2.sh脚本

3：重复执行aria2.sh脚本即可启动或关闭Aria2程序

#### 已Root用户：
1：使用文件管理器将Aria2文件夹放到系统分区任意目录下，如根目录：

```
/system
```

2：将该(Aria2)文件夹包括其内文件改权限为 0755(建议)

3：重复执行aria2.sh即可启动或关闭Aria2

## 管理使用

1：浏览器打开 https://voxhuang.github.io/aria2 进行查看和管理

```
https://voxhuang.github.io/aria2 
```

2：默认JSON-RPC为 http://localhost:6800/jsonrpc   密钥为 voxhuang.com

3：默认下载位置为 /Sdcard/Download

## 可选内容

1：optional文件夹下的内容为可选项，使用前无需将文件移动至 aria2.sh 同目录下

2；如果需要开机自启可以使用 daemon.sh，请注意这个脚本不是自动添加到系统启动项，您可以手动将其添加到任何可以执行脚本并且支持自启的程序中去
-->daemon.sh 有守护进程的作用，脚本默认以 每60秒间隔 检查Aria2的存活状态，如果Aria2异常关闭，则自动重启Aria2
-->daemon.sh 一旦执行将无法正常关闭，如需关闭，请先禁用脚本自启后重启设备，如需卸载，请先关闭程序然后使用卸载脚本卸载即可
-->daemon.sh 执行后无内容输出，切勿多次执行，并请注意 sleep 时间修改过短将可能导致设备卡顿或增加耗电量
-->daemon.sh 的监控功能在不同系统环境下并不一定总是有效，实际效果请自行测试

3：aconf.sh 用于简化配置文件，首次运行完成后原文件会被重命名为 aria2.conf.backup，再次运行会从aria2.conf.backup重新生成aria2.conf

4：error.sh 和 complete.sh 用于aria2.conf中的【 任务状态相关 】
-->error.sh 用于在下载出现错误时，通过Beep.dex播放音频文件error.wav，同时使用Chrome打开WebUI，但是如果Chrome正在运行则不会执行操作，避免在出现多个错误时重复运行
-->complete.sh 用于在下载全部完成时，通过Beep.dex播放音频文件complete.wav，但是如果在程序运行中通过WebUI临时更改下载路径，本脚本将不能正确工作
-->Beep.dex，dex2odex，error.sh，complete.sh 需要安装到系统目录后才能被调用，请用终端模拟器输入执行 sh /sdcard/Aria2/optional/Beep.sh 或用X-plore文件管理器点击脚本执行
-->error.wav，complete.wav 默认须放于脚本同目录下
-->Beep.dex，dex2odex 来自第三方，由于安卓系统差异化，这些程序并不一定能够在您设备上正常运行

5：aria2.conf 中必须定义脚本路径，根据安装器的不同，此路径也不相同，请查看aria2.info中 ADIR 的值，比如使用X-plore文件管理器安装的，其填写示例如

```
on-download-error=/data/data/com.lonelycatgames.Xplore/files/Aria2/error.sh
```



## 注意事项

1：在安装之前，您可以随意移动或修改文件夹名称，但是在安装之后相关配置文件中的路径便会成为固定值，这时请不要再随意移动或更改其文件夹名称

2：终端模拟器需支持 utf-8 编码，否则中文字符将不能正常显示，操作时请注意区分字母大小写，且免Root安装方式不能使用 su 超级用户权限

3：以普通用户权限运行时Aria2核心进程将继承宿主软件的用户标识，当使用黑域等软件时需要将宿主软件加入白名单，否则在宿主软件关闭退出时其名下所有子进程也将被结束运行

4；如果需要卸载，请用终端模拟器添加 -del 参数执行，如 sh /sdcard/Aria2/aria2.sh -del 或用文件管理器改名为del.sh再点击执行即可自动强制卸载

5：aria2.info为必要文件，记录了安装卸载等信息，由于某些脚本对其有依赖关系，请不要随意删除或更改其名称
-->如果需要更新Aria2核心，可以将新版本的 aria2c 文件放到脚本目录，然后删除aria2.info再次执行aria2.sh即可更新内核

6：由于用户组权限问题，使用X-plore文件管理器安装的Aria2，只有使用 X-plore文件管理器运行脚本才具备外置存储写权限
-->未Root用户，使用第三方软件调用脚本并运行的Aria2不具备外置存储写权限，请勿设置下载路径到外置存储
-->已Root用户，必须以ROOT用户身份运行Aria2，才能具备外置存储的写权限，并请确保外置存储路径填写正确


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
