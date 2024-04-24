# Dell-7460-OC-EFI
Dell Inspiron 7460 黑苹果 MacOS 14  Sonoma `DW1820A` EFI 

此 EFI 适用于戴尔燃 7000 系列第二代型号为 7460 的笔记本电脑。


## 电脑配置

| 规格     | 型号                                        |
| -------- | ------------------------------------------- |
| 电脑型号 | `Dell Inspiron 7460`                        |
| 操作系统 | `macOS Sonoma 14.4.1 (23E224)` |
| 处理器   | `Intel Core i7-7500U @ 2.70GHz` 双核        |
| 声卡     | `ALC256`                                    |
| 网卡     | 已更换为 `DW1820A`                           |



# EFI及启动盘制作

## 1. 准备一个 大于 16 GB 的 U盘 ，格式化成 FAT32 格式

## 2. EFI一键制作工具

[RapidEFI-Tool](https://github.com/JeoJay127/RapidEFI-Tool)

#### RapidEFI软件预览
![RapidEFI软件预览](https://github.com/JeoJay127/RapidEFI-Tool/blob/main/images/intel-desktop.png)

将生成 好的 EFI 拷贝到 U盘根目录


## 3. Mac OS 恢复镜像下载
通过 open Core 中的 [macrecovery](https://github.com/acidanthera/OpenCorePkg/tree/master/Utilities/macrecovery) 工具下载 MacOS 恢复镜像

参考 ：[downloading-macos](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/windows-install.html#downloading-macos)

将下载好的 系统恢复镜像 也拷贝到 U盘根目录

现在 U盘的目录结构应该是这样的
```shell
.
├── EFI
│   ├── BOOT
│   └── OC
└── com.apple.recovery.boot
    ├── BaseSystem.chunklist
    └── BaseSystem.dmg
```


## 4.接着就可以 重启电脑， 插入制作好的 U盘。 




# 系统优化
## 显示配置 HIDPI
[BetterDisplay](https://github.com/waydabber/BetterDisplay)

具体配置方法，请自行搜索。


## WIFI 驱动

由于 最新 Mac OS 系统中已经弃用 `AirPortBrcmXXX` 相关的驱动

[14]
- AirPortBrcm4360: removed
- AirPortBrcm4331: removed
- AirPortBrcmNIC: removed
- AirPortBrcmNIC-MFG: removed




可以通过 [`OpenCore-Legacy-Patcher`](https://github.com/dortania/OpenCore-Legacy-Patcher/) 工具，进行注入

可以通过 OCLP 的方式 驱动 WI-FI  ：[OCLP_WIFI](https://github.com/5T33Z0/OC-Little-Translated/blob/main/14_OCLP_Wintel/Enable_Features/WiFi_Sonoma.md)

