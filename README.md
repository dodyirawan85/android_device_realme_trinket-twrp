# android_device_realme_trinket
For building TWRP for Realme 5

TWRP device tree for Realme 5

## Features

Works:

- ADB
- Decryption of /data (Needs more testing)
- Screen brightness settings
- Correct screenshot color
- MTP
- Flashing (opengapps, roms, images and so on)
- Backup/Restore (Needs more testing)
- USB OTG
- Vibration support
- External sdcard

## Compile

First checkout minimal twrp with omnirom tree:

```
repo init -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_omni.git -b twrp-9.0
repo sync
```

Then add these projects to .repo/manifest.xml:

```xml
<project path="device/realme/realme_trinket" name="dodyirawan85/android_device_realme_trinket-twrp" remote="github" revision="android-9.0" />
```

Finally execute these:

```
. build/envsetup.sh
lunch omni_realme_trinket-eng
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

