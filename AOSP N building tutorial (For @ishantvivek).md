In the desired directory, initialize the Git repositories:
```
repo init -u https://github.com/TheComputerGuy96/android.git -b aosp-n
```
Do a repo sync to download all the sources:
```
repo sync
```
Then in the same directory where you did "repo sync", extract proprietary libraries and apply patches:
```
chmod +x device/samsung/kylepro/patch
device/samsung/kylepro/patch
patch -p1 < device/samsung/kylepro/AOSP\ N\ patches.diff
```
Finally, build the ROM:
```
. build/envsetup.sh
brunch kylepro
```