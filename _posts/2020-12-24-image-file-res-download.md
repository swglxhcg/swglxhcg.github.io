---
title: GrubFM ISO下载
date: 2020-12-24 17:17:34
author: "ChenZTai"
tags:
 - iso
 - resources
 - grub
 - download
categories:
 - grub
 - iso
---

GRUB下一个强大的文件管理器，可以支持启动U盘或硬盘上wim/iso/vhd/img/等格式文件（还支持网络哦）。

<!-- more -->

# 使用方法
## Grub4DOS
在menu.lst中加入如下内容：
```
title GrubFM
map --mem /grubfm.iso (0xff)
map --hook
chainloader (0xff)
```
## Grub2
将grubfm.iso文件复制到分区根目录，然后在自己机器上找到/usr/lib/syslinux/memdisk，复制一份，同ISO文件放在一起。
然后编辑/boot/grub/grub.cfg文件

```
menuentry 'GrubFM'{
        set root='(hd0,msdos1)'     #把iso所在分区设置成根目录
        echo 'Loading Memdisk...'
        #insmod memdisk
        linux16 /memdisk iso raw  //根目录下面的iso
        echo 'Loading ISO...'
        initrd16 /grubfm.iso
}
```
- 项目官网： [https://github.com/a1ive/grub2-filemanager](https://github.com/a1ive/grub2-filemanager)
- 下载地址：[https://chenztai.lanzous.com/ih85Uk7f8mh
密码:6kh6](https://chenztai.lanzous.com/ih85Uk7f8mh)