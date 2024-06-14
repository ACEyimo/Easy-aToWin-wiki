---
title: Easy-aToWin 简介<br>骁龙845/855等机型轻松从Android跨越到Windows
keywords: Easy-aToWin, Android, Windows, 刷机包, Windows刷机包, 安卓刷机包,  Windows11, Windows10, Windows 11 arm, Windows 10 arm, 安卓刷Windows, 小米刷Windows, 一加刷Windows, 红米刷Windows, 亦魔
desc: Easy-aToWin，轻松从Android跨越到Windows，一个从安卓到windows的刷机包
---

官网：[Easy-aToWin.ACEyimo.cn](https://Easy-aToWin.aceyimo.cn/)
本文档地址：[gitee.com/ACEyimo/Easy-aToWin-wiki](https://gitee.com/aceyimo/Easy-aToWin-wiki)
项目开源地址：[github](https://github.com/ACEyimo/Easy-aToWin-wiki) | [gitee](https://giee.com/ACEyimo/Easy-aToWin-wiki)

>! 本项目**永久免费**，且拒绝二次修改后**兜售转卖**。
> 如果发现有人**使用我的代码**还**收费**的，请及时**通知我!**
> **务必谴责**此类行为，提醒他人**本包免费，谨防上的受骗。**

> 下文又臭又长，可以不看。
----
## 项目由来
**WOA项目**实现了我曾经想在手机用上windows的梦。
大约两年之前，刚接触这个项目的时候（2022），就觉得不如刷安卓那样方便，始终是个遗憾。于是着手尝试制作成`一键刷机包`，当时也完成了一小部分。
然而有两个致命难题无法短时间解决，再加上项目官方不支持这种“傻瓜式操作”，且有一个恶意收费的“蛋”在，便搁浅了。

前段时间（大概在2024年5月）突然心血来潮，有点闲钱有点闲时，又开始重建这个项目。
开始的时候发现，小太阳ACA在很久之前就出过一个刷机包，还解决了一个难题（[BCDboot](https://github.com/BigfootACA/bcdboot)解决了REC环境下修复引导问题）。

兜兜转转，此项目已比较稳定，就此公开项目，目前全部代码为`Linux Shell 脚本`方式，修改难度较低，**欢迎其他开发者完善和适配**。

---
## 作者的话：
着手这个项目的时候，刚开始考虑**加密**和**收费**，之后再免费公开，原因是：  
+ 防止如之前“蛋”这种人恶意售卖。
+ 回收设备资金以支持其他机型更新。
+ 付费用户通常更积极参与反馈与建议。

原定计划是设备花费回笼和刷机包稳定后改成免费发布，但是想了想，似乎没必要。毕竟手机刷win的热度都过去了。
而且项目的众多维护者付出远比我多得多，收获却很少，我再去收费，反而寒了那些用爱发电的项目维护者。
所以痛定思痛，创建这个开源项目，将刷机包**代码优化至更加通用**，方便**其他开发者维护**，使其支持更多机型。

当然也不排斥捐赠，我会视捐赠情况酌情收几个其他设备进行适配，也大家欢迎进群反馈：172952046（QQ没事儿别加哈），
外国友人如果发现bug和提建议，可以发送邮件到 ACEyimo@qq.com

也可以提供设备供我测试和适配，但需**自行承担运费与风险**，归还时**无法保证设备状态**。
> 另外我还有个小要求：给我[B站视频](https://space.bilibili.com/10268297)**点赞投币**可好？
