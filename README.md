# Hackintosh-DELL-Optiplex-7060-7070MT-EFI

## Introdution
This is the Hackintosh EFI Folder for Dell OptiPlex 7060-7070MT. The configuration settings support macOS High Sierra (17G2112) Or Later. 

Reaktek ALC255 didn't work caused by IRQ conflicts, has been disable HPET.

## Hardware
* **CPU**: Intel® Core™ i5-8500
* **IGPU**: Intel® UHD Graphics 630
* **RAM**: 8GB DDR4 2666 Daul Channel
* **SSD**: APPLE SSD SM0128L Media & Samsung 860EVO
* **Wi-Fi & BT**: BCM943602CDP

## Working
* CPU Turbo Boost
* IGPU Accelerator Full Support (Metal2 HEVC H.264 Video De/EnCode )
* Realtek ALC255  (Microphone Work Needs VerbStub.kext & ComboJack)
* The First USB2.0 Port Near The Ethernet Interface is Disabled
* LAN & Wireless
* AirDrop & AirPlay
* Sleep Wake Support But Sometimes it can't be ShutDown after Wakeup

## Not working:
*DP Audio has been Disabled. Because Sleep Wake Kernel Panic. (Config.plist->Kernel->Quirks->PowerTimeOutPanic->True, to fix) 

## BIOS Settings
* System Configuration → SATA Operation: ***AHCI***
* Secure Boot → Secure Boot Enable: ***Disabled***

## Proposal BIOS Setting
* Security → PPT(TPM) → ***Disabled***
* System Configuration → Serial Port→ ***Disabled***
* Intel® Software Guard Extensions™ → Intel® SGX™ → ***Disabled***

## BIOS Settings via GRUBShell
* Set Pre-Allocated DVMT to 64M: 
***setup_var 0x8DC 0x02***
* Disable CFG lock: 
***setup_var 0x5BE 0x00***

## 简介
本EFI适用于 Dell OptiPlex 7060 7070MT 可支持macOS High Sierra (17G2112) 或更高版本

Reaktek ALC255 由于IRQ冲突无法加载AppleHDA.kext 已屏蔽HPET解决

## 硬件配置
* **CPU**: Intel® Core™ i5-8500
* **IGPU**: Intel® UHD Graphics 630
* **RAM**: 8GB DDR4 2666 Daul Channel
* **SSD**: APPLE SSD SM0128L Media & Samsung 860EVO
* **Wi-Fi & BT**: BCM943602CDP

## 可用
* CPU 睿频
* IGPU 加速器支持 (Metal2 HEVC H.264 视频编解码)
* Realtek ALC255  (使用麦克风需要VerbStub.kext + ComboJack)
* 仅保留15个USB端口可用，后置最靠近网线接口的USB2.0已屏蔽，第二个USB2.0连接蓝牙HCI
* 以太网 & Wi-Fi
* AirDrop & AirPlay
* 睡眠唤醒可用，但随即出现唤醒后关机重启死机问题

## 不可用:
*DP音频已屏蔽 由于唤醒后AppleHDAHDMI_DPDriver会导致setPowerState Kernel Panic (打开Config.plist->Kernel->Quirks->PowerTimeOutPanic->True, 也可解决)

## BIOS 设置
* System Configuration → SATA Operation: ***AHCI***
* Secure Boot → Secure Boot Enable: ***Disabled***

## BIOS 设置建议
* Security → PPT(TPM) → ***Disabled***
* System Configuration → Serial Port→ ***Disabled***
* Intel® Software Guard Extensions™ → Intel® SGX™ → ***Disabled***

## Setup Var
* Set Pre-Allocated DVMT to 64M: 
***setup_var 0x8DC 0x02***
* Disable CFG lock: 
***setup_var 0x5BE 0x00***

