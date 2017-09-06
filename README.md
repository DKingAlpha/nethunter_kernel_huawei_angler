## Kernel Base:
`git clone https://android.googlesource.com/kernel/msm -b android-msm-angler-3.10-oreo-r6`

## Patch:
```
kernel-3.10-oreo-angler.patch       Add HID suppport
mac80211-oreo-angler.patch          Add mac80211 Injection
oreo_r6_bug_fix.patch               Fix oreo_r6 bugs in bluetooth driver
```
## kali_defconfig: 
Configured as [Modifying the Kernel](https://github.com/offensive-security/kali-nethunter/wiki/Modifying-the-Kernel)


## Compile from scratch:

#### 1: Download kernel source tree
```
cd /opt
git  clone https://android.googlesource.com/kernel/msm  -b  android-msm-angler-3.10-oreo-r6
mv  msm  nethunter-kernel-oreo-angler
```

#### 2: Apply .patch
```
cd /opt/nethunter-kernel-oreo-angler
cp  $ThisRepo/*.patch  /opt/nethunter-kernel-oreo-angler
patch  -p1  < *.patch
rm  *.patch
```
#### 3: Apply config and Compile

```
cp  $ThisRepo/kali_defconfig  /opt/nethunter-kernel-oreo-angler/arch/arm64/configs/
cd /opt/nethunter-kernel-oreo-angler
make kali_defconfig

make -j14

```
