---
title: 从github构建
keywords: Easy-aToWin, Android, Windows, 刷机包, Windows刷机包, 安卓刷机包,  Windows11, Windows10, Windows 11 arm, Windows 10 arm, 安卓刷Windows, 小米刷Windows, 一加刷Windows, 红米刷Windows, 亦魔
desc: Easy-aToWin，轻松从Android跨越到Windows，一个从安卓到windows的刷机包
---

> 查看[设备特殊性](../../device/README.md)查找支持列表
## 下载
打开项目[Github](https://github.com/ACEyimo/Easy-aToWin)/[Gitee](https://gitee.com/ACEyimo/Easy-aToWin)，点击右上角的"Code"按钮，选择"Download ZIP"，下载[ZIP文件](https://github.com/ACEyimo/Easy-aToWin/archive/refs/heads/main.zip)。
或者，你也可以用git克隆仓库到本地：
```sh
git clone https://github.com/ACEyimo/Easy-aToWin.git
```
## 安装依赖
刷机包的制作需要7zip，请根据你的系统安装。
ubuntu：
```bash
sudo apt install p7zip-full
```
termux：
```bash
pkg install p7zip
```
## 生成刷机包
```sh
cd Easy-aToWin && chmod +x make.sh
# ./make.sh 手机代号 指定update-binary版本
# 第二参数可留空，默认使用updata-binary/new.sh
./make.sh enchilada A.bc20240514
```
## 使用
执行完成后，会在`out`文件夹生成三个包，按照[文件名说明](../filename.md)更改。