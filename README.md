# android_device_realme_trinket
For building TWRP for Realme 5

TWRP device tree for Realme 5

## Features

- [X] ADB
- [ ] Decryption of /data
- [X] Screen brightness settings
- [X] Correct screenshot color
- [X] Correct date/battery level/temperature
- [ ] MTP
- [ ] Flashing (opengapps, roms, images and so on)
- [ ] Backup/Restore (Needs more testing)
- [ ] USB OTG
- [X] Vibration support
- [X] External sdcard
- [ ] Reboot to bootloader/recovery/system

## Compile

First checkout minimal twrp with omnirom tree:

```
repo init -u git@github.com:minimal-manifest-twrp/platform_manifest_twrp_aosp.git -b twrp-12.1
repo sync
```

Then add these projects to .repo/manifest.xml:

```xml
<project path="device/realme/realme_trinket" name="realme-trinket-organization/android_device_realme_trinket-twrp" remote="github" revision="android-12.1" />
```

Finally execute these:

```
. build/envsetup.sh
lunch twrp_realme_trinket-eng
mka recoveryimage ALLOW_MISSING_DEPENDENCIES=true # Only if you use minimal twrp tree.
```

To test it:

```
fastboot flash recovery out/target/product/realme_trinket/recovery.img
```

Then reboot to recovery

## Other Sources

Using precompiled stock kernel

## Thanks

