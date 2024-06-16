---
title: 刷机流程和完成进度
keywords: Easy-aToWin, Android, Windows, 刷机包, Windows刷机包, 安卓刷机包,  Windows11, Windows10, Windows 11 arm, Windows 10 arm, 安卓刷Windows, 小米刷Windows, 一加刷Windows, 红米刷Windows, 亦魔
desc: Easy-aToWin，轻松从Android跨越到Windows，一个从安卓到windows的刷机包
---

1. [x] 验证机型
2. [x] 验证刷机包
3. [ ] 验证分区`[70%]`
   + [ ] 分区包
     - [ ] 验证是否官方分区`[50%]`
     - [ ] 验证分区大小是否正确`[50%]`
   + [ ] 刷写包
     - [x] 验证win和esp分区是否存在
     - [ ] 验证分区大小是否正确`[50%]`
4. [x] 执行操作
   + [x] 分区包
      - [x] 缩小userdata分区
      - [x] 创建esp和win分区
   + [x] 刷写包
      - [x] 安装win镜像和引导文件
      - [x] 备份安卓boot并刷入UEFI boot
   + [x] 恢复包：
      - [x] default：删除esp和win分区，扩大userdata分区
      - [x] auto：删除userdata及以后分区，重建userdata分区
      - [x] sgdisk：以指定的sgdisk备份恢复分区
5. [ ] 其他
   - [x] 读写配置`[未启用]`
   - [ ] 输出日志
   - [ ] 对UEFI引导配置文件进行修改
   - [ ] 其他还没想到
6. [x] 完成

> 大部分项目依赖读写配置来进行验证，但此函数未启用，所以只完成一部分。