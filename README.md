# DELL-inspiron-5488安装macOS Mojave
## 电脑配置

| 规格     | 详细信息                                     |
| -------- | ---------------------------------------- |
| 电脑型号 | DELL-inspiron-5488             |
| 处理器   | 英特尔 酷睿 i5-8265u处理器             |
| 内存     | 16GB  DDR4 2400MHz                 |
| 硬盘     | 西部数据 NVMe固态硬盘 sn520 256GB                  |
| 集成显卡 | 英特尔 UHD 图形620                            |
| 声卡     | 瑞昱 ALC236                     |
| 网卡     | 博通 DW1560                             |

### 我的触控板升级系统后无法使用。

你需要在每次更新系统后重建缓存。运行 `Kext Utility.app` 或者在 `终端.app` 输入 `sudo kextcache -i /`，然后重启。  


## 更新日志
### v1.1
昨天手贱更新bios位2.1.0出现了新问题，导致现在的之前上传的引导不能继续使用。会出现如下的错误。后来对比1.4.0的bios提取的dsdt发现RTC部分发生了变化,修改后能够正常开机，至此问题解决，由于觉得dsdt碍眼，又不会制作hotpatch，由冰水大佬帮忙制作hotpatch，问题解决抛弃dsdt。（升级2.1.0后的问题解决办法 
### v1.2
1:系统升级10.14.4,更新clover，10.14.3的机友替换引导可以直接升级。我升级没出问题。  
2:更换VirtualSMC.kext为Fakesmc.kext.之前有概率开机进不去开在显卡的位置。所以更换了fakesmc，好了一点点，没有彻底解决。今天遇到了一次。但是比用VirtualSMC.kext发生的概率小多了。  
3:升级后触摸板不能用，不要担心，清理缓存重启就好。  
4:本次引导上传分两个版本，一个是bios2.1.0以下的，一个是2.1.0使用的，奉劝各位不要更新bios，如果已经更新1.4.0的建议升级到2.1.0.因为我使用1.4.0睡眠有问题，概率睡眠唤醒重启。
###v1.3（2019年4月4日）
1:经过反馈，发现bios版本1.3.0也不能良好的睡眠。所以建议各位机友升级bios版本为2.1.0。现只提供2.1.0bios下使用的引导。  
2:添加启动参数，电池电量可自动刷新。  
### v1.4（2019年4月10号）
重新仿冒声卡，参照ID99做了修改。解决睡眠唤醒无声。去掉输入的音频线路输入。耳麦还是没搞定。（自行打开alc_fix双击打开install双击自动安装.command输入密码。执行声卡守护。）
### v1.5
1:重新仿冒声卡制作ID：54。  
2:BIOS更新为2.2.2版本。  
3:更换网卡为bcm94360cs2.建议基友都可以更换，比dw1560便宜。  
4:蓝牙概率睡眠唤醒掉驱动，增加ssdt修复。这个可能需要根据自己的实际情况作修改。可以选择删除。  