
# Acer Aspire E5-576G-59S6 Hackintosh

macOS Big Sur on Acer E5-576G-59S6 with OpenCore 0.6.6 EFI folder
<img src="https://github.com/techgenius1/E5-576G-59S6-Hackintosh-OpenCore/blob/master/BigSur576G.png?raw=true" alt="look">

## Configuration

| Specifications      | Detail                                      |
| ------------------- | ------------------------------------------- |
| Computer model      | Acer Aspire E 15 E5-576G (MX150)            |
| BIOS Version        | Acer v1.49                                  |
| Processor           | Intel Core i5-8250U Processor               |
| Memory              | 12GB DDR3 1600MHz                           |
| Integrated Graphics | Intel UHD Graphics 620                      |
| Sound Card          | Realtek ALC255 (layout-id:30)               |
| Wireless Card       | Intel Wireless 8160                         |
| Touchpad            | Synaptics I2C Touchpad                      |



## What's not working (Never will work) ⚠️

- [ ] Nvidia MX150
- [ ] Card Reader

## Current Status in OpenCore

- Discrete graphic card is not working, since macOS doesn't support Optimus technology
  - Have used [SSDT-DGPU](EFI/OC/ACPI/SSDT-DGPU.dsl) to disable it in order to save power
- Using a HDMI-VGA adapter to connect an external monitor causes lag and black screen for unknown reason, but using either a HDMI-HDMI or VGA-VGA direct connection is fine.
- Everything else works well

## Installation

### First-time installation

- Please refer to the following installation tutorials
  - [Xiaomi Mi Notebook Pro MacOS Catalina Installation Guide || ENGLISH](https://bit.ly/34biTqw)
- You can refer to the following tutorials for additional configuration
   - https://dortania.github.io/vanilla-laptop-guide/
- You should add Serial Number, UUID, MLB and ROM details to Config -> PlatformInfo -> Generic if you want to get iServices working.

- If you intend to dual boot Windows on the same drive, it is recommended that you install macOS **first** then use BootCamp to install Windows everything should work fine.
- It is highly recommended that you use [ProperTree](https://github.com/corpnewt/ProperTree) or OpenCore Configurator to make any changes to the config.plist in `\EFI\OC`, otherwise you may corrupt the file.
- Add `BOOT` and `OC` folders to your EFI partition.

## FAQ

### My touchpad isn't working after update.

You need to rebuild the kext cache after every system update. Use `Kext Utility.app` or type `sudo kextcache -i /` in `Terminal.app`. Then restart. If this still doesn't work, try to press F9.

### My screen turns to black and has no response during the updating process.

If you have black screen for five minutes and get no response from the device, please force restart your laptop(Long press power button) and choose `Boot macOS Install from ~` entry.


## Credits
- Thanks to [jianminglok](https://github.com/jianminglok/E5-576G-Hackintosh) for providing EFI for E5-576G
- Thanks to [Acidanthera](https://github.com/acidanthera) for providing [AppleALC](https://github.com/acidanthera/AppleALC), [AppleSupportPkg](https://github.com/acidanthera/AppleSupportPkg),  [Lilu](https://github.com/acidanthera/Lilu), [OcBinaryData](https://github.com/acidanthera/OcBinaryData), [OpenCorePkg](https://github.com/acidanthera/OpenCorePkg), [VirtualSMC](https://github.com/acidanthera/VirtualSMC), [VoodooInput](https://github.com/acidanthera/VoodooInput), [VoodooPS2](https://github.com/acidanthera/VoodooPS2), and [WhateverGreen](https://github.com/acidanthera/WhateverGreen).
- Thanks to [alexandred](https://github.com/alexandred) for providing [VoodooI2C](https://github.com/alexandred/VoodooI2C).
- Thanks to [daliansky](https://github.com/daliansky) for providing [OC-little](https://github.com/daliansky/OC-little), the template for this Readme, many valuable samples in patching SSDT and various ACPI patches for OpenCore.
- Thanks to [jsassu20](https://github.com/jsassu20) for providing samples for [patching the brightness keys i ACPI](https://github.com/jsassu20/OpenCore-HotPatching-Guide/tree/master/17-Brightness%20Shortcut%20Patch).
- Thanks to [Sniki](https://github.com/Sniki) for providing [OS-X-USB-Inject-All](https://github.com/Sniki/OS-X-USB-Inject-All).
- Thanks to [corpnewt](https://github.com/corpnewt) for providing [USBMap](https://github.com/corpnewt/USBMap) and [ProperTree](https://github.com/corpnewt/ProperTree).
- Thanks to [zxystd](https://github.com/zxystd) for providing [IntelBluetoothFirmware](https://github.com/zxystd/IntelBluetoothFirmware).
