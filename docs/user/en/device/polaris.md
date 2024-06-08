---
title: MIX2S 特殊说明
keywords: Easy-aToWin, Android, Windows, 刷机包, Windows刷机包, 安卓刷机包,  Windows11, Windows10, Windows 11 arm, Windows 10 arm, 安卓刷Windows, 小米刷Windows, 一加刷Windows, 红米刷Windows, 亦魔
desc: Easy-aToWin，轻松从Android跨越到Windows，一个从安卓到windows的刷机包
---

>! 目前发现橙狐REC的**R11.1_3_unified**版本会导致刷机包不可能，请使用TWRP或橙狐正式版(**R11.1_1**)及之前的版本。

> 小米MIx2s需要专用`devcfg.img`才能正常触屏和启动，以及会有`基带丢失`的问题。
> 声音因为未并入edk2-WOA项目，需要专用驱动和UEFI镜像，此机型针对这三个问题进行适配和解决。

## 下载镜像
推荐使用[某贼的懒人包](https://www.123pan.com/s/8eP9-5YvGA.html)：`MIX2S懒人包-正式第一版-感谢Sunflower2333大佬制作的音频驱动-2023.12.11-1.mtip`
[移动云盘](https://caiyun.139.com/m/i?1N5BTrmyIWXco)提取码：**DKef**
---

## 分区包
无特殊性，正常刷入即可

---

## 刷写包
刷写包内置两个UEFI Boot 版本，一个是**Sunflower2333**制作的`声音驱动`专用版本，一个是官方项目的`v2.0rc2`版本。两者兼容的驱动不同，不能混用，**默认刷入官方版**。
如果你使用包含声音驱动的镜像，按照规范修改刷写包文件名，在**输入值**插入`audio`字样，示例：
flash-polaris-`Win11_22H2_audio`-all-V1.3.4.2.zip
### 占位符
刷写包占位符接受三个参数，**区分大小写**：
+ **devcfg**：MIUI需要专用`devcfg.img`镜像，输入此值会刷入devcfg.img。非MIUI**好像**不需要。
+ **modem**：使用此值会自动备份基带，并生成一个**恢复基带刷机包**。生成完成后会复制到`/sdcard/`目录下，备份分区包含：`modem`、`modemst1`、`modemst2`、`fsc`、`fsg`
+ **all**：上述两者都会启用。
> 假设你要刷入包含声音的wim镜像，同时你是MIUI，但已手动备份好基带，那么刷机包名类似是这样：
> flash-polaris-**Win11_22H2_audio**-**devcfg**-V1.3.4.2.zip
> 此名称会使用以Win11_22H2_audio开头、wim结尾的镜像，并刷入devcfg.img，但不会备份基带。

----

## 恢复包
恢复包的特殊性只需要修改 **占位符** 。此值主要为刷写包擦屁股。
接受的参数`all`或包含`devcfg`、`modem`、`boot`的值，**区分大小写**：
+ **devcfg**：恢复备份的devcfg，目前不恢复也没发现什么问题。
+ **modem**：恢复备份的基带。
+ **boot**：恢复备份的安卓boot。
+ **all**：上述三者全部启用。
> 如果启动多项，以 **_** 符号分割，如：`boot_devcfg_modem`。此值等同于all。
> 假设你使用auto模式恢复，只需要恢复安卓boot和devcfg，那么刷机包名类似这样：
> reset-polaris-auto-boot_devcfg-V1.3.4.2.zip
由于不恢复devcfg也不影响MIUI正常使用，刷写包还会生成一个基带包。**通常来说什么也不需要启用**，默认为`null`即可。只要在恢复包之前提前把基带恢复包备份好，恢复之前自行刷入安卓boot就好。

---

## 更新日志
2024年6月4号首次添加mix2s的支持，顺便发现了update-binary的几处bug，顺手又优化了make.sh脚本，然后**机型日志忘了写**！