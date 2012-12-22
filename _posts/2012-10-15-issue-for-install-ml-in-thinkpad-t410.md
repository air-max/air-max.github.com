---
layout: post
title: ThinkPad T410安装mountain lion 碰到的问题
categories:
- Mac osx
tags:
- T410
- Thinkpad
- 黑苹果 
---


#1: 安装盘启动PCI configuration begin 错误

Kernel Flags 设置成
npci=0×2000

#2: win版变色龙不能加载DSDT， 需要转换到mac版变色龙

Win版变色龙转换到Mac版变色龙
转自http://bbs.pcbeta.com/forum.php?mod=viewthread&tid=891022

方法A（此法要求mac所在分区为主分区或者逻辑分区的第一个或最后一个分区）
要求：MAC系统盘所在分区为主分区或者为扩展分区的第一分区或最后一个分区：
1.Win版变色龙引导进入MAC系统；
2.安装PKG格式的变色龙（默认路径，不用改，变色龙到kexts.com去下载）；
3.修复权限，重启，U盘PE进入DiskGenius分区工具：
a.如果原来MAC系统盘为主分区，右键单击MAC系统盘——激活当前分区，保存更改。
b.如果原来MAC系统盘所在分区为扩展分区第一分区或者最后一个分区，右键单击MAC系统盘所在分区，转换为主分区，保存更改，然后再次右键单击，激活当前分区，保存更改。
4.如果win版变色龙在mac系统盘下的Extra文件夹还在可以直接用，没有了的请手动新建，在MAC系统盘分区根目录新建Extra，将dsdt.aml，com.appleboot.plist，smbios放入Extra（有则放无则跳过），然后在Extra里面新建Extensions文件夹，放入fakesmc.kext和其他的驱动文件，Extra下也可以新建theme的主题文件夹等，具体不赘述了；
5.重启，检查效果（在成功前不要轻易删除Win版变色龙）。

这样声卡，显卡就完美了。


