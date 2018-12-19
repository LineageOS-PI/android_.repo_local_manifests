Local manifests to build LineageOS 16.0 for [Raspberry Pi 3].

How to build:
-------------

1. Set up [Android build environment](https://source.android.com/setup/initializing).

2. Install additional packages:

```
sudo apt-get install kpartx python-mako
```

3. Initialize repo:

```
repo init -u git://github.com/LineageOS/android.git -b lineage-16.0
git clone https://github.com/LineageOS-PI/android_.repo_local_manifests .repo/local_manifests -b lineage-16.0
repo sync
```

4. Compile:

```
. build/envsetup.sh
lunch lineage_rpi3-userdebug
mka kernel ramdisk systemimage vendorimage
```

5. Create writable image:

```
cd device/brcm/rpi3
sudo ./mkimg.sh
```
