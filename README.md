# Dell OptiPlex3080 MFF Hackintosh
 
个人在用黑苹果小主机，买回来之后装了 Monterey 用过一段时间，后来升级 Venture 时没有完全搞懂导致引导不了了，重装系统也不能解决，就换回 Windows 在用。最近又来了冲动，在网上看了些相关的介绍，又莫名其妙的可以用了。

这个机器在印象中所有的介绍都提到要解锁 CFG，之前时没有搞定的，这次折腾后差不多理解了，通过一个牛人的 EFI 里带的工具解锁了。目前在用 Monterey 系统。

EFI 源自 [PCBETA]()，通过 OCAT 将 OC 升级到了目前的最新版本 1.0.2，Kext 没有升级。在原 EFI 的基础上我禁掉了 NVMeFix.kext，不然的话会在引导阶段卡住。

基于目前的配置，短时间内看睡眠可以通过鼠标和键盘唤醒（之前用的时候时不行的，必须要把休眠关掉）。接下来的计划：

* USB 端口定制
* 增加 Intel Wi-Fi（自带的，在BIOS里现禁用掉了）
* 尝试下看是否有机会升级 Sonoma

## BIOS 设置

|Settings|Value|
|----|---|
|System Configuration → Integrated NIC | Enabled |
|System Configuration → SATA Operation | AHCI |
|Security → PTT Security/PTT On | Disabled |
|Secure Boot → Secure Boot Enable | Disabled |
|Secure Boot → Secure Boot Mode | Audit Mode |
|Intel SGE → SGX | Disabled |
|Performance → Intel SpeedStep | Enabled |
|Performance → C-States Control | Enabled |
|Performance → Turboost | Enabled |
|Performance → HyperThread Control | Enabled |
|Power Management → Intel Speed Shift Technology | Enabled |
|Power Management → Deep Sleep Control | Disabled |
|Power Management → USB Wake Support | Disabled |
|Power Management → Wake on LAN/WLAN | Lan only |
|Power Management → Block Sleep | Disabled |
|POST Behavior → Fastboot | Minimal |
|Virtualization Support → Virtualization | Enabled |
|Virtualization Support → VT For Direct I/O | Disabled |
|Advanced configurations → ASPM | Auto |

以上设置引用自： https://github.com/jerryhan77/dell-optiplex-7080mff-opencore
关于修改DVMT和CFG LOCK 也可以参考上面的链接，我目前只解锁了CFG，DVMT没有动。

## 黑苹果工具
* https://dortania.github.io/OpenCore-Install-Guide/
* https://github.com/dortania/OpenCore-Legacy-Patcher
* ProperTree: https://github.com/corpnewt/ProperTree
* GenSMBIOS: https://github.com/corpnewt/GenSMBIOS
* gibMacOS：https://github.com/corpnewt/gibMacOS
* Hackintool：https://github.com/headkaze/Hackintool
* USBMap：https://github.com/corpnewt/USBMap
* OCAT: https://github.com/ic005k/OCAuxiliaryTools/