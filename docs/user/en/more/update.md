---
title: update-binary更新日志
keywords: Easy-aToWin, Android, Windows, 刷机包, Windows刷机包, 安卓刷机包,  Windows11, Windows10, Windows 11 arm, Windows 10 arm, 安卓刷Windows, 小米刷Windows, 一加刷Windows, 红米刷Windows, 亦魔
desc: Easy-aToWin，轻松从Android跨越到Windows，一个从安卓到windows的刷机包
---

## 版本说明
<p><span style="font-weight:bold">示例：</span>
<span style="color:blue; font-weight:bold">A</span>.<span style="color:red; font-weight:bold">b</span><span style="color:green; font-weight:bold">c</span><span>20240423</span>
</p>

+ <span style="color:blue; font-weight:bold">A</span>：代码重构或大更新
+ <span style="color:red; font-weight:bold">b</span>：功能更新时或较大BUG修复
+ <span style="color:green; font-weight:bold">c</span>：修复BUG或局部代码优化
+ **20240423**：发布时间
---

## 更新日志
### A.cd20240604
+ 修复恢复包sgdisk模式未正常运行的bug
+ 修复无法备份安卓boot的bug
+ 优化可能导致异常删除esp分区文件的bug
+ 对分区包增加重建分区的备选方案
+ 对打印的提示风格进行了统一
+ 优化wim镜像查找规则
### A.cc20240516
+ 新增恢复包函数
+ 修复了几个小bug
### A.bc20240514
+ 修复了无法发送备份文件到sdcard的bug
### A.bb20240423
+ 增加了写入和读取配置函数
### A.ab202404??
+ 优化了部分情况导致刷机包不可用的bug
### A.aa202404??
+ 初代版本，完善大部分功能
### beta1.2
+ 内测版本，忘了写日志
---

## 刷机包版本说明
刷机包版本对应update-binary的版本：`A -> 1`，`b -> 2`，`c -> 3`......以此类推
例如使用A.bc20240423的刷机包，刷机包版本号为**v1.2.3**。
部分刷机包可能会多一位，则表示维护者主动设置了`追加版本号`，一般无需理会，详情参考机型的说明文档。