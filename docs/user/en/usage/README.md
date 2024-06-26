---
title: Easy-aToWin 快速指南
keywords: Easy-aToWin, Android, Windows, 刷机包, Windows刷机包, 安卓刷机包,  Windows11, Windows10, Windows 11 arm, Windows 10 arm, 安卓刷Windows, 小米刷Windows, 一加刷Windows, 红米刷Windows, 亦魔
desc: Easy-aToWin，轻松从Android跨越到Windows，一个从安卓到windows的刷机包
---
>! **刷机包依赖文件名，请严格按照规则命名，切勿随意修改！**   **\[**详情参照[文件名说明](fileName.md)**\]**

## 刷机前准备
+ [TWRP](https://twrp.me/Devices/)等第三方REC
+ [刷机包](./download/)
+ [WIndows镜像](./download/win.md)
+ 最好带上**脑子**
---

## 刷机包类型
+ **分区包**(`part`)：对分区进行调整，创建安装Windows需要的分区。
+ **刷写包**(`flash`)：刷入Windows系统，创建引导记录。
+ **恢复包**(`reset`)：恢复分区为出厂预设值。
---

## 快速入手
>! 建议在最新的`官方系统`[^系统]和官方分区下操作，可以避免大部分问题。
1. **刷入part包（分区包）**
   - 重启到Recovery
   - 格式化data分区
   - 重启到系统（这一步很重要）
2. **重启到Recovery**
3. 备份boot分区
4. **刷入flash包（刷写包）**
5. 重启，然后享受
> 因为分区包会导致手机数据清空，避免重复下载，**分区完成后再下载`刷写包`和`Win镜像`**。当然你可以一次性下载完后放置在`U盘`里
---

## 其他说明
1. 刷写包完成后会自动向`/sdcard/`目录下发送当前boot分区备份，但我仍然建议提前**手动备份**好`boot`和`基带`[^基带]。  
2. 如果你想要换win系统，先恢复`安卓boot`镜像，再刷一遍刷写包即可。  
3. 我不建议使用非官方系统安装此项目刷机包，这可能导致一些未知问题[^问题]。如果你执意如此：
    + 我建议在刷入**分区包后、刷写包之前**更换你想要的安卓镜像，这可以避免很多问题，**但不绝对**！
    + 未分区前如果你使用动了分区的安卓镜像，这**极有可能**出现未知问题。
    + 已安装完Win系统后，提前备份好`Win boot`，再更换安卓镜像。
---
## 以后想到别的再补充
---
[^系统]:双分区手机A和b分区需要保持一致，简单方法是在已安装最新版的系统里复刷一遍。
[^基带]:基带丢失会导致失去`sim卡通讯`、`IEMI`丢失等问题，且`9008`无法拯救。备份时勾选**EFS、Modem**（基带）即可。
[^问题]:非官方系统可能因为环境、依赖等不同，导致出现刷机失败及未知错误。一旦出现问题，很有可能**9008都无法恢复**。