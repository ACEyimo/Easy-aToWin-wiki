---
title: 制作Winodws镜像
keywords: Easy-aToWin, Android, Windows, 刷机包, Windows刷机包, 安卓刷机包,  Windows11, Windows10, Windows 11 arm, Windows 10 arm, 安卓刷Windows, 小米刷Windows, 一加刷Windows, 红米刷Windows, 亦魔
desc: Easy-aToWin，轻松从Android跨越到Windows，一个从安卓到windows的刷机包
---

>! **没写完**，直接用我或者某贼网盘制作好的镜像吧，不同CPU的制作方法不统一，写起来又臭又长
> 当然，你非要自己的做，原理就是`挂载原版wim镜像` -> `添加驱动` -> `保存镜像`。剩下的参照项目文档吧：[woa-msmnile](https://woa-msmnile.github.io/InstallationGuides/InstallDrivers.html) | [Renegade Project](https://renegade-project.tech/zh/install)。全量包就是**已进入Winodws桌面**后再`另存为镜像`。

Linux/Android环境为Windows系统添加驱动方法，不说没可能吧，至少现阶段没发现有人做过。所以需要一台**Windows 设备**用来自制一个**包含驱动的WIM镜像**。
> 我更推荐下载我已经制作完成的镜像，或者去[某贼的网盘](https://www.123pan.com/s/8eP9-5YvGA.html)里扒拉个懒人包。
## 准备材料
1. 一台运行windows的设备
2. 原版Wim arm镜像
3. [Dism++](https://github.com/Chuyu-Team/Dism-Multi-language/releases/latest)
4. 驱动包

## 材料获取
对于只有手机的用户而言，可以使用云电脑来解决无windows设备的问题。国内的阿里无影云电脑和移动云电脑等可以免费体验一段时间。

**原版镜像：**
+ 使用[UUPdump](https://www.uupdump.cn/)生成最新且集成更新的镜像。或者直接从微软[官网下载](https://www.bilibili.com/video/BV1hb4y1W7kC)。
+ Linux或手机可以直接使用我网盘里附带的两个镜像，或参考我的[B站视频](https://www.bilibili.com/video/BV1hb4y1W7kC)用uupdump生成镜像，但都`不集成更新`。

**驱动包：**
+ 骁龙845机型：从小太阳ACA提供的[下载网站](https://download.renegade-project.tech/)获取。或者项目的[开源地址](https://github.com/edk2-porting/WOA-Drivers/releases/)下载。
+ 骁龙855机型：参考项目开源地址[msmnile-Drivers](https://github.com/woa-msmnile/msmnile-Drivers)的README.md说明获取。
+ 骁龙835等其他机型：搜了半天没找全，我建议从某贼Mindows工具箱里获取到的网盘地址找吧。
  - 打开 Mindows工具箱 > 选择/切换机型 > 下载/更新机型资源。然后打开 `Mindows工具箱/bin/tmp/update-dlres.txt` 就看到了
  - 或者直接选择你的机型，等下载完成后： `Mindows工具箱/bin/res/手机型号/woa/drive` 就是驱动包的所有文件了。
.. details::update-dlres.txt 2024-05-27
    ```python
    1:[sagit],小米6,2023.10.15-1,syxz.lanzn.com/iui7K1buc4gf,暂无,2023.8.19-1,syxz.lanzn.com/ij33v15w9nja,暂无,blank,blank,暂无,blank,blank,暂无 
    2:[wayne],小米6X,2023.12.23-1,syxz.lanzn.com/i1DDL1iuw1ud,暂无,2023.12.23-1,syxz.lanzn.com/iaDjY1itm49e,暂无,blank,blank,暂无,blank,blank,暂无 
    3:[dipper],小米8,2023.9.12-1,syxz.lanzn.com/iCbM0184643c,无,2023.8.19-1,syxz.lanzn.com/i6DdV169ez4f,暂无,blank,blank,暂无,blank,blank,暂无 
    4:[equuleus],小米8屏幕指纹版,2023.10.15-1,syxz.lanzn.com/ikk1I1bubl2h,暂无,2023.8.19-1,syxz.lanzn.com/iOiTH16bm5ja,暂无,blank,blank,暂无,blank,blank,暂无 
    5:[ursa],小米8透明探索版,2023.8.19-1,syxz.lanzn.com/iMYkS17ntgxa,更新分区表恢复文件,2023.8.19-1,syxz.lanzn.com/iQ0JH16bmjje,暂无,blank,blank,暂无,blank,blank,暂无 
    6:[cepheus],小米9-小米9透明尊享版,2024.1.20-1,syxz.lanzn.com/iYlOK1loi87a,更新安卓14TWRP,2024.2.17-1,[syxz.lanzn.com/iGMtS1ok5zne][syxz.lanzn.com/iZsyg1ok62ed],USB默认文件传输模式（充电需要切换），更新GPU，修复AI键。注意：必须使用比Win10-18363更高的版本。建议使用Win11-22H2或更高版本。,blank,blank,暂无,2024.1.12-1,[syxz.lanzouo.com/iT5FD1kuwg6b][syxz.lanzouo.com/iPJwo1kuwjbe],修复右键。注意：必须使用比Win10-18363更高的版本。建议使用Win11-22H2或更高版本。 
     7:[chiron],小米MIX2,2023.10.30-1,syxz.lanzn.com/iqlQc1d8uivc,更新官方分区表,2023.8.19-1,syxz.lanzn.com/irQnD16c06ta,暂无,blank,blank,暂无,blank,blank,暂无 
    8:[polaris],小米MIX2S,2023.9.12-1,syxz.lanzn.com/i3xMU1846ute,无,2023.12.7-1,syxz.lanzn.com/iGsht1h44t8j,修复声音,2023.9.12-1,syxz.lanzn.com/i3xMU1846ute,无,2023.12.7-1,syxz.lanzn.com/iGsht1h44t8j,修复声音 
    9:[perseus],小米MIX3,2023.9.24-1,syxz.lanzn.com/iblWJ19rucej,更新资源,2023.8.19-1,syxz.lanzn.com/igscB16bsori,暂无,blank,blank,暂无,blank,blank,暂无 
    10:[andromeda],小米MIX3_5G,2023.8.19-1,syxz.lanzn.com/igZwP169frod,暂无,2023.8.19-1,[syxz.lanzn.com/iUL0f16btgih][syxz.lanzn.com/i5cLA16btc1g][syxz.lanzn.com/i57wv16btchc],暂无,blank,blank,暂无,blank,blank,暂无 
     11:[jason],小米Note3,2023.8.19-1,syxz.lanzouo.com/iZeA01kdi5qj,暂无,2023.8.19-1,syxz.lanzouo.com/iFr0H1kdi9uh,暂无,blank,blank,暂无,blank,blank,暂无 
    12:[beryllium],小米POCOF1,2023.8.19-1,syxz.lanzn.com/iJZSw169ftgh,暂无,2023.8.19-1,syxz.lanzn.com/iaJuX16bzsre,暂无,blank,blank,暂无,blank,blank,暂无 
    13:[vayu],小米POCOX3Pro,2023.8.19-1,syxz.lanzn.com/iqVKV169go3a,暂无,2023.8.19-1,[syxz.lanzn.com/iiU5n16c3j5c][syxz.lanzn.com/ivjLZ16c3dja][syxz.lanzn.com/iVAnr16c3god],暂无,blank,blank,暂无,blank,blank,暂无 
     14:[nabu],小米平板5,2024.1.3-1,[syxz.lanzn.com/igOAI1jx3mpe][syxz.lanzn.com/iyaW31jx44li],增加安卓14TWRP,2024.3.10-1,[syxz.lanzoue.com/iBITj1qzcfxi][syxz.lanzoue.com/ie7D81qzcl8j],同步Github更新,blank,blank,暂无,2024.1.15-1,[syxz.lanzn.com/iEPnB1l6rolg][syxz.lanzn.com/ivptO1l6rpri],【警告：本次更新驱动前必须先更新主程序到最新！】修复官方键盘，WiFi蓝牙。更多详见Github。 
    15:[pipa],小米平板6,2024.3.19-1,syxz.lanzoue.com/i6bET1rxbule,更新128GB官方分区表,2024.1.2-1,syxz.lanzn.com/iFKYM1jrh59e,暂无,blank,blank,暂无,blank,blank,暂无 
    16:[raphael],红米K20Pro-红米K20Pro尊享版,2023.9.24-1,syxz.lanzn.com/i0Bij19rup2f,更新256GB分区表恢复文件,2023.12.24-1,[syxz.lanzn.com/iXkGJ1ise6kd][syxz.lanzn.com/ilmeB1ise7kj][syxz.lanzn.com/iYDdT1iseb9c],更新UEFI，修复亮度调节。,blank,blank,暂无,blank,blank,暂无 
     17:[shark],黑鲨1,2023.9.12-1,syxz.lanzn.com/i5P0p184460j,暂无,2024.1.27-1,syxz.lanzoue.com/ifXt11r7srmd,更新WiFi，声音，GPU驱动。但驱动尚不稳定，目前推荐使用打好驱动的懒人包。,blank,blank,暂无,blank,blank,暂无 
    18:[bullhead],黑鲨Helo,2023.8.19-1,syxz.lanzn.com/iGGuf169lfjc,暂无,2023.8.19-1,syxz.lanzn.com/ifoCb16d1feb,暂无,blank,blank,暂无,blank,blank,暂无 
    19:[OnePlus5],一加5,2023.10.15-1,syxz.lanzn.com/iKLov1bubswj,暂无,2023.8.19-1,syxz.lanzn.com/id52w16d1fuh,暂无,blank,blank,暂无,blank,blank,暂无 
     20:[OnePlus5T],一加5T,2023.10.15-1,syxz.lanzn.com/idw9u1buc2da,暂无,2023.8.19-1,syxz.lanzn.com/i89MB16d1gib,暂无,blank,blank,暂无,blank,blank,暂无 
     21:[OnePlus6],一加6,2023.11.26-1,[syxz.lanzn.com/i0rBf1fyxgvg][syxz.lanzn.com/ivCdV1fyxigd],更新256GB官方分区表,2023.8.19-1,syxz.lanzn.com/ijjHR16d1huj,暂无,blank,blank,暂无,blank,blank,暂无 
    22:[OnePlus6T],一加6T-一加6T迈凯伦版,2023.8.19-1,syxz.lanzn.com/ijQAj16bb32f,暂无,2023.8.19-1,syxz.lanzn.com/ics0K16d1i8d,暂无,blank,blank,暂无,blank,blank,暂无 
    23:[OnePlus7Pro],一加7Pro_4G,2023.8.19-1,[syxz.lanzn.com/imSIo16bgfrc][syxz.lanzn.com/i8sZt16bghhe],暂无,2023.10.15-1,[syxz.lanzn.com/iFZdS1buw3ud][syxz.lanzn.com/iiJqs1buw90j][syxz.lanzn.com/ia7CH1buwaza],更新UEFI和驱动,blank,blank,暂无,blank,blank,暂无 
     24:[OnePlus7T],一加7T,2023.8.19-1,syxz.lanzn.com/i8rm916bgqmd,暂无,2023.8.19-1,syxz.lanzn.com/iVxgm16d1ipa,暂无,blank,blank,暂无,blank,blank,暂无 
    25:[OnePlus7TPro],一加7TPro_4G-一加7TPro迈凯伦版_4G,2023.10.30-1,[syxz.lanzn.com/ibnAQ1d8v1di][syxz.lanzn.com/i07tg1d8ve7a],更新安卓13TWRP（注：TWRP连不上电脑请手动重启TWRP再试）,2024.3.1-1,[syxz.lanzoue.com/ijjQE1pxiysf][syxz.lanzoue.com/iw0001pxj69e][syxz.lanzoue.com/ipevU1pxjd1i],同步驱动更新，支持声音外放,blank,blank,暂无,2024.2.18-1,[syxz.lanzn.com/iVhwm1onqrbi][syxz.lanzn.com/iki961onquid],同步Github更新 
    26:[OnePlus7TProNR],一加7TPro迈凯伦版_5G,2023.8.19-1,syxz.lanzn.com/i8oWs16bh4za,暂无,2023.8.19-1,syxz.lanzn.com/i5y8i16d1r1a,暂无,blank,blank,暂无,blank,blank,暂无 
    27:[TP1803],努比亚mini5G,2023.8.19-1,syxz.lanzn.com/iTlZJ16bhcyh,暂无,2023.8.19-1,[syxz.lanzn.com/ieeQb16d1z9g][syxz.lanzn.com/iFlJA16d1xbg][syxz.lanzn.com/i9uEH16d1y1c],暂无,blank,blank,暂无,blank,blank,暂无 
    28:[NX616J],努比亚X,2023.10.15-1,syxz.lanzn.com/i0e151bucoze,无,2023.9.12-1,syxz.lanzn.com/iDcY217iwj9c,更新触摸，WiFi，GPU，息屏,blank,blank,暂无,blank,blank,暂无 
    29:[NX563J],努比亚Z17,2023.8.19-1,syxz.lanzn.com/iW2BB16bhn3c,暂无,2023.11.10-1,syxz.lanzn.com/ifbjy1efeceb,尝试添加一些驱动,blank,blank,暂无,blank,blank,暂无 
    30:[NX595J],努比亚Z17S,2023.8.19-1,syxz.lanzn.com/idX4o16bhr3g,暂无,2023.8.19-1,syxz.lanzn.com/ik2vG16d24yb,暂无,blank,blank,暂无,blank,blank,暂无 
    31:[NX606J],努比亚Z18,2023.8.19-1,syxz.lanzn.com/iGQnV16bhvhe,暂无,2024.1.3-1,syxz.lanzn.com/iSit51jx14od,USB，触摸，GPU，移动数据，蓝牙等大部分功能可用，NFC，扬声器不可用,blank,blank,暂无,blank,blank,暂无 
     32:[NX619J],红魔Mars-红魔2,2023.8.19-1,syxz.lanzn.com/isQHJ16bi0vi,暂无,2023.8.19-1,syxz.lanzn.com/iiisB16d27gb,暂无,blank,blank,暂无,blank,blank,暂无 
    33:[judyln],LGG7,2023.9.12-1,syxz.lanzn.com/i6PCq1849pud,无,2023.8.19-1,syxz.lanzn.com/i7uKN17ti1re,暂无,blank,blank,暂无,blank,blank,暂无 
    34:[alphaplus],LGG8,2023.8.19-1,syxz.lanzn.com/iP8EY17puw7i,暂无,2024.1.14-1,[syxz.lanzouo.com/iARr41l4gwid][syxz.lanzouo.com/iWGyO1l4gx3e],修复WiFi，蓝牙，定位，触摸（可能需要手动更新驱动），声音（可能需要手动更新驱动），GPU（理论可用），亮度（理论可用）,blank,blank,暂无,blank,blank,暂无 
    35:[mh2lm],LGG8X,2023.8.19-1,[syxz.lanzn.com/izrd617iwumb][syxz.lanzn.com/iJ3La17iwv7c],暂无,2023.8.19-1,[syxz.lanzn.com/inUxx16d2foh][syxz.lanzn.com/i4AcK16d2dri][syxz.lanzn.com/iKy0516d2dub],暂无,blank,blank,暂无,blank,blank,暂无 
     36:[judypn],LGV40,2023.8.19-1,syxz.lanzouo.com/iEbKR1ldwfpi,暂无,2023.8.19-1,syxz.lanzn.com/iYIDM1lamulg,暂无,blank,blank,暂无,blank,blank,暂无 
    37:[flashlmdd],LGV50,2023.8.19-1,syxz.lanzn.com/ilA4y17ixw3a,暂无,2023.8.19-1,syxz.lanzn.com/iBap416d2iwd,暂无,blank,blank,暂无,blank,blank,暂无 
    38:[mh2lm_5g],LGV50S,2023.8.19-1,syxz.lanzn.com/iTQri16bj2vg,暂无,2023.8.19-1,[syxz.lanzn.com/iANev16d2pjc][syxz.lanzn.com/ivaaY16d2qaj],暂无,blank,blank,暂无,blank,blank,暂无 
    39:[16th],魅族16th,2023.10.15-1,syxz.lanzn.com/iRMEU1bucz1g,暂无,2023.8.19-1,syxz.lanzn.com/i7A7316d2utc,暂无,blank,blank,暂无,blank,blank,暂无 
    40:[16thPlus],魅族16thPlus,2024.3.15-1,syxz.lanzoue.com/iDF811ri9s8h,增加128GB官方分区表，增加修复UEFI显示卡顿的xbl.img,2024.3.15-1,syxz.lanzoue.com/i6hM61ri9gzc,更换可用驱动和UEFI,blank,blank,暂无,blank,blank,暂无 
    41:[PAFM00],OPPOFindX标准版,2023.10.15-1,syxz.lanzn.com/iQ4JR1bucl5g,暂无,2023.11.29-1,syxz.lanzn.com/iRyfF1gct1za,USB，蓝牙可用，其余不可用,blank,blank,暂无,blank,blank,暂无 
    42:[PAHM00],OPPOFindX高配版,2023.12.10-1,syxz.lanzn.com/iv5A91hf5p3c,暂无,2023.12.10-1,syxz.lanzn.com/igRkR1hf5xqd,暂无,blank,blank,暂无,blank,blank,暂无 
    43:[R11],OPPOR11,2023.12.23-1,syxz.lanzn.com/iEZFR1itljnc,暂无,2023.12.23-1,syxz.lanzn.com/iyE9U1itm33c,暂无,blank,blank,暂无,blank,blank,暂无 
    44:[OP46C3],OPPOReno10X-OPPOReno10倍变焦版,2023.8.19-1,syxz.lanzn.com/iQBgC16bjmkf,暂无,2023.8.19-1,syxz.lanzn.com/isee016d33uh,暂无,blank,blank,暂无,blank,blank,暂无 
    45:[trident],坚果R1,2023.8.19-1,syxz.lanzn.com/iiijN16bjwyj,暂无,2023.8.19-1,syxz.lanzn.com/iusrr16d369e,暂无,blank,blank,暂无,blank,blank,暂无 
    46:[ASUS_I001_1],华硕ROGPhone2,2023.8.19-1,syxz.lanzn.com/iaJqe17iyk9a,暂无,2024.3.1-1,[syxz.lanzoue.com/i5OVt1pwmqob][syxz.lanzoue.com/iM8nL1pwmu5g],修复触摸，声音；减小GPU故障概率,blank,blank,暂无,blank,blank,暂无 
    47:[P845A02],中兴天机Axon9,2023.8.19-1,syxz.lanzn.com/ia5OY16bkdfc,暂无,2023.8.19-1,syxz.lanzn.com/ijSxA16d3auj,暂无,blank,blank,暂无,blank,blank,暂无 
    48:[linus],雷蛇2,2023.8.19-1,syxz.lanzn.com/ioGRP16bkhcd,暂无,2023.8.19-1,syxz.lanzn.com/ifb2O16d3dhe,暂无,blank,blank,暂无,blank,blank,暂无 
    49:[mata],EssentialPhone,2023.9.12-1,syxz.lanzn.com/ikonM1848src,暂无,2023.8.19-1,syxz.lanzn.com/iumyX16d3f0j,暂无,blank,blank,暂无,blank,blank,暂无 
    50:[duo],SurfaceDuo,2023.10.15-1,syxz.lanzn.com/i47Cw1bubfcb,暂无,2024.1.16-1,[syxz.lanzn.com/iUlWw1lb7sod][syxz.lanzn.com/iFTS31lb7u0b][syxz.lanzn.com/imny91lb7wra][syxz.lanzn.com/iQx8Y1lb7xwb][syxz.lanzn.com/iL4HK1lb7zhi][syxz.lanzn.com/iOPPd1lb820j],同步Github驱动更新,blank,blank,暂无,blank,blank,暂无 
    ```


>未完待续....