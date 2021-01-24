# Hackintosh on Asrock H370 pro4 Code via [OpenCore][OC]

![About this mac][System Info]

*macOS Supported:* **10.14+**

This is light configuration to run macOS smoothly. I didn't get any [kernel panics][uptime] science after macOS install. This config is base on [OpenCore Vanilla Desktop Guide][Guide].

## Hardware configuration

* Intel Core i5 8400  UHD630 (Geekbench 5: [CPU][GB_CPU]/[OpenCL][GB_OCL]/[Metal][GB_MTL])
* Asrock H370 pro4
* 2×8GB Adata XPG 2666MHz
* M.2 NVME ADATA SX6000NP 120GB
* ST2000DM001-1ER164 (FusioDrive)
* Atheros 9380 WIFI
* Bluetooth Roketek 4.1

## Before you start make sure you have

* Working hardware
* [BIOS][BIOS] version `>= 2102`
* Actual [OpenCore][OC] `= 0.6.4`
* Populated `PlatformInfo > Generic` section in `config.plist`, can be easyly done with `macserial` tool from [OpenCore][OC] utilities.

# Installation

## BIOS Settings

* *Exit* → Load Optimized Defaults [Yes]
* *Advanced* → System Agent (SA) Configuration → VT-d [**Disable**]
* *Advanced* → System Agent (SA) Configuration → Primary Display [**IGPU**]
* *Advanced* → System Agent (SA) Configuration → DVMT Pre-Allocated [**64M**]
* *Advanced* → USB Configuration → Legacy USB Support [**Disabled**]
* *Advanced* → CPU Configuration → Intel Virtualization Technology [**Enabled**]
* *Boot* → Fast Boot [**Disabled**]
* *Boot* → CSM (Compatibility Support Module) → Launch CSM [**Disabled**]

## What's behind the scenes

You must download all not bundled kexts and drivers from repositories by yourself.

### Kexts

* [IntelMausi.kext][IntelMausi] - Another intel driver for Ethernet
* [AppleALC.kext][AppleALC] - Getting audio to work as easy-peasy
* [Lilu.kext][Lilu] - Dependency of `VirtualSMC.kext` and `WhateverGreen.kext`
* [VirtualSMC.kext][VirtualSMC] - A advanced replacement of FakeSMC, almost like native mac SMC.
* [WhateverGreen.kext][WG] - Need for GPU support (even for disabling discrete GPU)


### EFI drivers

* ~VirtualSMC.efi~ - only needed if you use File Vault 2 or [authrestart][FV2].

## Issues


## USB ports mapping


## Chnagelog
###### 07/10/2019
* The initial push to GitHub

[AppleALC]: https://github.com/acidanthera/AppleALC
[BIOS]: https://www.asus.com/Motherboards/ROG-MAXIMUS-X-CODE/HelpDesk_BIOS/
[FV2]: https://lifehacker.com/bypass-a-filevault-password-at-startup-by-rebooting-fro-1686770324
[GB_CPU]: https://browser.geekbench.com/v5/cpu/4261705
[GB_MTL]: https://browser.geekbench.com/v5/compute/1671274
[GB_OCL]: https://browser.geekbench.com/v5/compute/1671254
[Guide]: https://dortania.github.io/OpenCore-Desktop-Guide/
[IntelMausi]: https://github.com/acidanthera/IntelMausi
[Lilu]: https://github.com/acidanthera/Lilu
[OC]: https://github.com/acidanthera/OpenCorePkg
[System Info]: https://eljnavas.files.wordpress.com/2021/01/info.png
[uptime]: https://i.imgur.com/OGl5UDI.png
[VirtualSMC]: https://github.com/acidanthera/VirtualSMC
[WG]: https://github.com/acidanthera/WhateverGreen

