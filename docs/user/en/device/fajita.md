---
title: 一加6T 特殊说明
keywords: Easy-aToWin, Android, Windows, 刷机包, Windows刷机包, 安卓刷机包,  Windows11, Windows10, Windows 11 arm, Windows 10 arm, 安卓刷Windows, 小米刷Windows, 一加刷Windows, 红米刷Windows, 亦魔
desc: Easy-aToWin，轻松从Android跨越到Windows，一个从安卓到windows的刷机包
---
>! 未在一加6T进行测试，因为没有手机，刷机包和文档一律**照搬一加6**。理论两者通用，如有问题欢迎反馈

>一加6经常在WIndows安装过程中出现高通崩溃模式，推荐使用某贼的懒人包：`一加6懒人包Win11_22621.2265.230822_by某贼.mtip`，可极大程度避免此现象发生。
> 分区完成后，会出现中文字体缺失及内置储存不可用。这是因为氢系统对`userdata`分区加密所致。无法直接解决，只提供一个折中方案。


## 下载镜像
PS：这个是一加6T的
[移动云盘](https://caiyun.139.com/m/i?1N5BTXr09n9uZ)提取码：**Adbo**

---

## 特别说明
> 务必确保 A、B 分区刷入相同安卓系统、TWRP 及 root。若不确定，先复刷一次。建议使用 **OxygenOS 10/11** 系统

### Hydrogen
**S2vzznb**给出的解决方案：
+ 内置储存不可用：删除`/data/media`
+ 字体和软件缺失：从官分卡刷包的**payload**文件中提取**reserve**和**india**，依次复制到`/data/reserve/`、`/data/india/`
或者另外一种办法：
分区完成后，在 TWRP 中刷入当前系统全量包，使用官方 REC 执行“格式化设备”。
全量包获取：访问[阿木大侠云盘](https://yun.daxiaamu.com/OnePlus_Roms)
### OxygenOS
此系统无data加密，但分区后会缺少预装软件（包括浏览器）。解决方法：
将分区包的**占位符**设为 "via"，会自动发送Via浏览器至系统分区（ab都会发一遍）。有了浏览器约等于有了一切！
分区包名示例：part-enchilada-auto-`via`-v1.3.4.zip
> 有一个bug，切换到其他分区时via不可用，懒得研究能用就行
### 其他说明
启动windows UEFI时，点击`UEFI Boot Menu`，拉到最底部点击`Reboot to other slot`选项会重启到第二分区（boot_a或_b）。
重启后可进入第二分区的安卓，如果想再切换到windows在twrp里切换分区就可以了  
最终的状态是一个boot分区为启动windows，另外一个启动安卓。

---

## 更新日志
此机型为项目初期的测试机型，所以此机型的前期更新与主线一致，具体参照update-binary[更新日志](../more/update.md)