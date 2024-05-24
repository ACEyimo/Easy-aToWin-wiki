---
title: 刷机包文件名说明
keywords: Easy-aToWin, Android, Windows, 刷机包, Windows刷机包, 安卓刷机包,  Windows11, Windows10, Windows 11 arm, Windows 10 arm, 安卓刷Windows, 小米刷Windows, 一加刷Windows, 红米刷Windows, 亦魔
desc: Easy-aToWin，轻松从Android跨越到Windows，一个从安卓到windows的刷机包
---

>! 所有属性的值**必须严格遵循规则**，禁止使用除"**`_`**"和"**`.`**"以外的特殊字符。所有非法值导致的后果自负！！！

## 刷机包属性
文件名以“**`-`**”符号分割，共有五个属性：
<p>
<span style="color:blue; font-weight:bold">类型</span> -
<span style="color:red; font-weight:bold">型号</span> -
<span style="color:green; font-weight:bold">输入值</span> -
<span style="color:purple; font-weight:bold">占位符</span> -
<span style="color:orange; font-weight:bold">版本</span> .zip
</p>
<p>
<span style="color:blue; font-weight:bold">part</span> -
<span style="color:red; font-weight:bold">polaris</span> -
<span style="color:green; font-weight:bold">auto</span> -
<span style="color:purple; font-weight:bold">null</span> -
<span style="color:orange; font-weight:bold">stable1.3</span> .zip
</p>
<p>
<span style="color:blue; font-weight:bold">flash</span> -
<span style="color:red; font-weight:bold">dipper</span> -
<span style="color:green; font-weight:bold">Win11_21H2</span> -
<span style="color:purple; font-weight:bold">null</span> -
<span style="color:orange; font-weight:bold">stable1.3</span> .zip
</p>
<p>
<span style="color:blue; font-weight:bold">reset</span> -
<span style="color:red; font-weight:bold">enchilada</span> -
<span style="color:green; font-weight:bold">default</span> -
<span style="color:purple; font-weight:bold">null</span> -
<span style="color:orange; font-weight:bold">beta1.2</span> .zip
</p>

---

## 属性说明
### 类型
标识刷机包类型。**不能修改**，会报错。
### 型号
指定手机型号，**不能修改**，会报错。
### 输入值
刷机包会根据此属性的内容不同执行不同的操作，以下是作用：
+ 分区包：用于设定Win分区大小
+ 刷写包：用于查找Windows镜像
+ 恢复包：设置恢复分区的模式
此值可根据需要进行修改，但**不能留空**，具体接受参数参照[输入值说明](#输入值说明)。
### 占位符
由于`部分机型`的特殊性，此属性用于对特殊机型适配，或以后开发新功能时预留。具体情况参考[设备特殊性](../devices/README.md)。  
此属性默认为null，未启动时修改也无效，但不能留空。
### 版本
略，不推荐修改，**不可留空**。

---

## 输入值说明
### 分区包
分区包会根据输入值设定Win分区大小，接受`两种值`，分别是：
+ **auto**：根据手机容量自动分配Win分区大小：
  - 64GB手机：Win分区大小为38GB
  - 128GB：70GB
  - 256GB：120GB
  - 512GB：240GB
  - ≥512GB：480GB
+ **整数**(G/gb)：手动指定Win分区大小，示例为“128Gb”。要求：
  - 数值不能小于38G。
  - 计算后手机剩余空间必须保留19G以上。
> 自定义容量不区分大小写，单位可省略。对于容量超过256GB的设备，推荐手动设定Win分区大小。
### 刷写包
刷写包的值是`Win镜像`文件名，系统将按以下**顺序**在指定路径查找匹配文件：
1. U盘：`/usbstore/`
2. 内置储存：`/sdcrad/`
3. 下载目录：`/sdcard/Download/`
查找规则：
+ 查找以`输入值`开头，`.wim`结尾的**首个文件**。
+ 如未找到，继续按路径顺序查找以`.mtip`结尾的**首个文件**。

> `.mtip`是 **某贼** Mindows工具的懒人包命名方案，这里指**全量包**[^全量包]。如果你打算使用全量包或者自定义包，“输入值”无需修改。
### 恢复包
用于设定恢复分区时的模式，接受`三种值`，分别是：
+ default：默认模式，只删除`Win`和`EFI`分区，调整userdata分区到100%。
+ auto：自动模式，删除官方`userdata分区编号`及以后的**所有分区**，重建userdata分区。
+ sgdisk：使用sgdisk分区备份文件进行恢复，优先使用EFI分区里手动备份的，如果没有再使用恢复包data文件夹下的备份。
> 默认模式适应于**只用过此项目分区包调整的分区**，如果你手动或使用其他工具调整过分区，可能到时恢复失败及未知问题。
> 自动模式适应大部分情况，但如果你删除过其他分区（如：system_b），可能导致恢复失败或分区错乱等问题。
 
>! sgdisk恢复分区的方法**我没用过**，所以不清楚什么情况会导致什么问题，欢迎[反馈](#)。

## 占位符
详情请查看[设备特殊性](../devices/README.md)，此栏目**必看**！

## 版本
由项目自动生成，以update-binary版本为准，详情参考[更新日志](other/update.md)。

---

[^全量包]:这里的全量包是`已经进过系统的镜像`，已包含了完成系统安装后的状态，无需经历常规安装后的系统初始化、驱动安装等步骤。相较于原版镜像能大幅减少安装问题（如蓝屏），显著缩短耗时。但可能预装特定软件，更改了系统设置等情况。  