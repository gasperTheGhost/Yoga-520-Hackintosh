# Yoga 520 Hackintosh
Lenovo Yoga 520-14IKB Hackintosh EFI partition with support for macOS Catalina 10.15.14 

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
  - Brightness controls expect F14 and F15 so must be set manually to F11 and F12
- Battery indicator

### Untested
- HDMI output
- USB C port

### What DOESNT Work
- Internal WiFi (unsupported card Qualcomm Atheros QCA9377, can be replaced with [one of the supported Broadcom cards](https://www.tonymacx86.com/threads/broadcom-wifi-bluetooth-guide.242423/))
- TouchID (probably never will)
- Hotkeys (Refresh, Airplane mode, Lock, Webcam On/Off, Mic On/Off)
- Messages and FaceTime (Probably a consequence of incompatible network card)
