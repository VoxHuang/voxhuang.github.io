---
layout: article
title: '华硕Padavan固件使用迅雷快鸟详细操作'
key: 15
category: Document
tags:
- Padavan
- 迅雷快鸟
- 路由器
---

## 操作步骤
1.安装好 [python](https://www.python.org/downloads/windows/)

2.下载 [Xunlei-Fastdick](https://github.com/fffonion/Xunlei-Fastdick/archive/master.zip)

3.解压

4.解压后的文件夹放进D盘并在里面新建 swjsq.account.txt 文件，内容:aaaaa,bbbbb（即快鸟帐号密码 PS:输入法切换英文状态时输入)>>保存

![avatar](https://voxhuang-blog-1253764139.cos.ap-shanghai.myqcloud.com/Xunlei-Fastdick-A.png)

5.完成以上步骤后，在PC上直接双击运行swjsq.py看是否能成功加速。（提前安装好python不然无法打开）闪退失败，成功有界面，最后关闭

6.成功加速后，同目录会生成对应的ipk和sh，以及加密后的.swjsq.account

![avatar](https://voxhuang-blog-1253764139.cos.ap-shanghai.myqcloud.com/Xunlei-Fastdick-B.png)

7.现在打开路由看图操作

```
FastDicks=2
uid="快鸟账号"
pwd="快鸟密码"
```

![avatar](https://voxhuang-blog-1253764139.cos.ap-shanghai.myqcloud.com/Xunlei-Fastdick-C.png)

8.按上图设置完毕后再以[Notepad++](https://notepad-plus-plus.org/download/)打开swjsq_wget.sh，把swjsq_wget.sh的内容文本全复制

![avatar](https://voxhuang-blog-1253764139.cos.ap-shanghai.myqcloud.com/Xunlei-Fastdick-D.png)

9.最后一步，路由器>>系统管理>>恢复/导出/上传设置>>提交(保存/etc/storage/内容到内存)

![avatar](https://voxhuang-blog-1253764139.cos.ap-shanghai.myqcloud.com/Xunlei-Fastdick-E.png)
