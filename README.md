# HP15DA-0XXX-OPENCORE
Opencore Hackintosh for HP 15-da0xxx. I'm using always latest BIOS version, OpenCore, additional kexts and macOS.\
**Current version is 100% macOS 11.1 Big Sur compatible!**\
For my specific laptop configuration almost everything works except WiFi which I am planning to upgrade to Intel AX200.\
I'm still working on improvement and clean ups.

## Massive overhaul
Hack is now based almost on pure OpenCore patches and hack. I followed [this guide](https://dortania.github.io/OpenCore-Install-Guide/) and [this tool](https://opencore.slowgeek.com/). 

Huge thanks to [Acidanthera team](https://github.com/acidanthera) for [OpenCore](https://github.com/acidanthera/OpenCorePkg).\
Extra credit goes to [@usr-sse2](https://www.hackintoshshop.com/2810/hackintosh-big-sur-guide/) for the most fail-safe comprehensive guide and base image file.

## Installation instructions

1. Put whole EFI folder into you EFI partition (you can try USB drive at first).
2. Generate your own serial numbers with [GENSMBIOS](https://github.com/corpnewt/GenSMBIOS) generator and change corresponding values (MLB, SystemSerialNumber, SystemUUID) in EFI/OC/config.plist according this [GUIDE](https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/kaby-lake.html#starting-point).
3. [Pay attention to HP Users:](https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/kaby-lake.html#cleaning-up.
4 Boot to macOS.
5. **IMPORTANT!** If you want to install macOS, you need to change property **ScanPolicy** to **0** along with **ShowPicker** to **true** in EFI/OC/config.plist otherwise you don't see BaseSystem option in OpenCore boot menu!

### My configuration

- Intel Core i5-8250U
- Intel UHD 620
- 16 GB DDR4 (2x 8GB)
- Full HD non-touch display (1920x1080)
- SAMSUNG MZNTD256HAGL 256GB M.2 SSD NVMe

## BIOS settings

Currently I'm using BIOS F.33. and latest released version of macOS 11.1 Big Sur.\
Start with BIOS reset to defaults and then disable all kind of security and TPM.
System works well with Fastboot enabled, but for debugging and playing with your setup is better to disable Fast Boot.
It's also recommended to disable Intel TXT technology and then disable Virtualization Technology for Directed I/O (VTd). OpenCore config disables this instead.

### Currently not working + solutions

- Bundled Realtek RTL8821CE 802.11ac PCIe Adapter\
  - Need to be replaced (cca. 15 USD) solution is [Fenvi Dual Band Wireless M.2 Wifi6 Intel AX200 2974Mbps Bluetooth 5.1 802.11ax MU-MIMO NGFF Laptop WiFi Card AX200NGW](https://www.aliexpress.com/item/4000563277082.html?spm=a2g0o.productlist.0.0.4b394d15rRh1vt&algo_pvid=cb56b6f4-8257-4db8-ab80-e0234487d7cf&algo_expid=cb56b6f4-8257-4db8-ab80-e0234487d7cf-8&btsid=0b0a555816095040205066880eafad&ws_ab_test=searchweb0_0,searchweb201602_,searchweb201603_) that fits into laptop perfectly. The best thing - there is already proven working kext (https://openintelwireless.github.io/itlwm/Compat.html).
- Hibernation (I just turn it off).
- DRM (Apple TV+, Netflix in Safari), but there is workaround use different browser ([Vivaldi](https://vivaldi.com) for me). There is also web version of [Apple TV+](https://tv.apple.com) that works from browser.
