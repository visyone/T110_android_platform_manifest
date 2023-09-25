# Platform Manifest Repository

## Requirements To Build

- A decent CPU
- 8GB of RAM
- 100GB of storage
- JDK 6
- [Android Build Dependencies](https://source.android.com/setup/build/initializing#setting-up-a-linux-build-environment)

## How To Set Up Minimal LineageOS-20 Sources

```bash
repo init --depth=1 -u git://github.com/LineageOS/android.git -b lineage-20.0
git clone git://github.com/visyone/android_platform_manifest.git .repo/local_manifests && rm -rf .repo/local_manifests/.git/
repo sync -c --force-sync --optimized-fetch --no-tags --no-clone-bundle --prune -j$(nproc --all)
```

## How To Build

```text
. build/envsetup.sh
lunch lineage_goya[product = wifi|3g]-[buildtype = eng|user|userdebug]
mka [target = bacon, otapackage, bootimage etc.]
```

**e.g.**

```shell
. build/envsetup.sh
lunch lineage_goyawifi-eng
mka bacon
```

