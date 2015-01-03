Recovery for Sony Devices
=========================

Sadly, this is probably **not** what you were expecting.

This is simply a cache of CyanogenMod Recovery `ramdisk-recovery.img` files for each Sony device supported in AOSP 5.0 Lollipop.

### What is this for?
---

Two major challenges face AOSP developers of Xperia devices:

1. Sony devices cannot boot into the recovery partition.
2. Custom recoveries such as ClockworkMod or TWRP cannot be built with AOSP.

**So how do we install OTA based scripts such as Gapps?**

Easy hack: put the recovery in the boot partition!

With this script the device's LED will shine purple on boot. During this time the user can press and hold Volume+ to enter recovery.

### How do I use this?
---

You need to define these in your device repo:

1. BOARD_CUSTOM_BOOTIMG := true
2. BOARD_CUSTOM_BOOTIMG_MK := device/sony/recovery/custombootimg.mk

You will also need these two commits in your /build folder:

1. [1ba97de5ae66175c8c8c6a54285b2a8562917f17](https://github.com/CyanogenMod/android_build/commit/1ba97de5ae66175c8c8c6a54285b2a8562917f17)
2. [22913dea82299eac7e1a5e754102b89af4796a0d](https://github.com/CyanogenMod/android_build/commit/22913dea82299eac7e1a5e754102b89af4796a0d)
