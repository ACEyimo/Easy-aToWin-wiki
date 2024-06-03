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
cd Easy-aToWin && chmod +x make.sh
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
`./make.sh 手机代号`
命令执行完成后会在`out/手机型号/`目录下生成刷机包
以一加6为例：
```sh
./make.sh enchilada
```
可选项：`-o 输出指定的包`
默认值all，可选参数（part/flash/reset）
示例，此命令结束后会在`out/手机型号/`下生成`分区包`：
```sh
./make.sh enchilada -o part
```

## 使用
执行完成后，会在`out/手机型号/`文件夹生成三个包，按照[文件名说明](../filename.md)更改。然后刷入即可