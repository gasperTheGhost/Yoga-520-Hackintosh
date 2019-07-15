# Yoga 520 Hackintosh
Lenovo Yoga 520-14IKB Hackintosh EFI partition and installation notes for macOS Mojave 10.14.5

**This build is a Work In Progress**

## Features
### What Works
- Keyboard
- USB 3.0
- Full TrackPad support
- Touchscreen and active stylus (tested with Wacom Bamboo Ink)
- Graphics acceleration
- Speakers and 3,5mm jack
- Microphone
- Built-in card reader
- Sleep and hibernation (with delay)
- Bluetooth
- Webcam
- Hotkeys (Audio controls, TrackPad On/Off)
- Battery indicator

### Untested
- HDMI output
- USB C port

### What DOESNT Work
- Internal WiFi (unsupported card Qualcomm Atheros QCA9377, can be replaced with [one of the supported Broadcom cards](https://www.tonymacx86.com/threads/broadcom-wifi-bluetooth-guide.242423/))
- TouchID (probably never will)
- Hotkeys (Refresh, Airplane mode, Lock, Brightness controlls, Webcam On/Off, Mic On/Off
- Messages and FaceTime

## Installation notes
1. Installation was done using a Unibeast USB (RehabMan's Clover build would not boot) with [RehabMan's HD 620 config.plist](https://github.com/RehabMan/OS-X-Clover-Laptop-Config/blob/master/config_HD615_620_630_640_650.plist) on a secondary machine. This can be avoided by using the EFI partition posted here for booting the installer.
2. At this point booting worked only in safe mode (ig-platform-id: 0x12345678 caused kernel panic), BT and USB 3.0 worked out of the box
3. After installation [Hackintool 2.6.9](https://www.tonymacx86.com/threads/release-hackintool-v2-6-9.254559/) was used for framebuffer patching using Kaby Lake Platform ID 0x591B0000
4. Card reader support was enabled using [Sinetek-rtsx.kext](https://github.com/sinetek/Sinetek-rtsx) (Placed inside /EFI/CLOVER/kexts/Other)
5. Audio was enabled with AppleALC.kext and layout ID 15
6. TrackPad support was enabled with [VoodooI2C.kext and VoodooI2CHID.kext](https://github.com/alexandred/VoodooI2C) and [patching the DSDT](https://voodooi2c.github.io/#Installation/Preparing%20your%20machine%20for%20VoodooI2C) with Windows 10 patch in MaciACL
7. Hibernation was fixed by setting hibernationmode to 25 in [Hackintool 2.6.9](https://www.tonymacx86.com/threads/release-hackintool-v2-6-9.254559/)
8. Battery and charging indication was enabled using [RehabMan's ACPIBatteryManager.kext](https://github.com/RehabMan/OS-X-ACPI-Battery-Driver), which also seemed to enable full TrackPad support (before this right click and tap to click did not work)
