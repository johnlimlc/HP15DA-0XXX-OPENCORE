# HP15DA-0XXX-OPENCORE
Opencore Hackintosh for HP 15-da0xxx. I'm using always latest BIOS version, OpenCore 0.8.6, additional kexts and macOS.\
**Current version is 100% macOS 13.0.1 Ventura compatible!**\
For my specific laptop configuration almost everything works except WiFi which I am planning to upgrade to Intel AX200.\
I'm still working on improvement and clean ups.

## Massive overhaul
Hack is now based almost on pure OpenCore patches and hack. I followed [this guide](https://dortania.github.io/OpenCore-Install-Guide/) and [this tool](https://github.com/ic005k/OCAuxiliaryTools). 

Huge thanks to [Acidanthera team](https://github.com/acidanthera) for [OpenCore](https://github.com/acidanthera/OpenCorePkg).\
Extra credit goes to [olarila](https://www.olarila.com) for the most fail-safe comprehensive guide and base image file.

## Installation instructions

1. Put whole EFI folder into you EFI partition (you can try USB drive at first).
2. Generate your own serial numbers with [GENSMBIOS](https://github.com/corpnewt/GenSMBIOS) generator and change corresponding values (MLB, SystemSerialNumber, SystemUUID) in EFI/OC/config.plist according this [GUIDE](https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/kaby-lake.html#starting-point).
3. [Pay attention for HP Users:](https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/kaby-lake.html#cleaning-up).
4. Boot to macOS.
5. **IMPORTANT!** If you want to install macOS, you need to change property **ScanPolicy** to **0** along with **ShowPicker** to **true** in EFI/OC/config.plist otherwise you don't see BaseSystem option in OpenCore boot menu!

### My configuration

- Intel Core i5-8250U
- Intel UHD 620
- 16 GB DDR4 (2x 8GB)
- Full HD non-touch display (1920x1080)
- SAMSUNG MZNTD256HAGL 256GB M.2 SSD NVMe

## BIOS settings

Currently I'm using BIOS F.42. and latest released version of macOS 13.0.1 Ventura.\
Start with BIOS reset to defaults and then disable all kind of security and TPM.
System works well with Fastboot enabled, but for debugging and playing with your setup is better to disable Fast Boot.

Many thanks to all who make it works!
