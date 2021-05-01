# Install Custom ROM: AOSP
I just search internet for a the fastest ROM I could install and from the results, I took one that the installation was well documented

Following: https://forum.xda-developers.com/t/rom-nzh54d-2021-03-05-asus-nexus-7-2012-wifi-3g-f2fs-ext4-android-7-x-aosp.3467514/

## Perform a Factory Reset
1. Restarted the tablet into Fastboot by long pressing `Volume Down` and `Power`.
2. Go to `Recovery Mode`. TWRP should appear
3. Tab `Wipe`
4. Swipe to `Factory Reset`

## Install AOSP
1. Download AOSP 7.1.2 Tilapia OTA-Package (Build 20210305) from https://androidfilehost.com/?fid=2188818919693747769
2. Open a terminal in Mac and move yourself into the folder that contains the ZIP file
3. Connect the tablet to the MAC
4. Verify that the tablet is connected and available `adb devices`. You should see a device there
```
List of devices attached
015d3b668467e80f	recovery
```
5. Copy the ZIP file into the tablet `adb push aosp* /sdcard`
6. In the main screen on TWRP, Tab `Install`
7. Tab the file you just copied
8. Swipe to confirm Flash. It will install the image
9. Reboot into Recovery

## Install Gapps
The Nexus 7 2012 3G and this AOSP version needs the following selection og Gapps:
* ARM (no ARM64)
* 7.1
* pico

1. Download the right Gapps from https://opengapps.org/
2. Once in TWRP, copy the ZIP file into the tablet `adb push open_gapps* /sdcard`
3. In the main screen on TWRP, Tab `Install`
4. Tab the file you just copied
5. Swipe to confirm Flash. It will install the image

In my case I received an `error 70`, with an explanation that there is `Insufficient storage space available`
* Deleted the faulty gapps file: `adb shell rm -f /sdcard/open_gapps-arm-7.1-pico-20210428.zip`. Specifying the full filename is mandatory.
* I downloaded a previous version of Gapps: `open_gapps-arm-7.1-pico-20191213.zip` from https://androidfilehost.com/?fid=2188818919693784514
* Copied it into the tablet
* 

## Finish the installation
Once the AOSP and the Gapps are installed, we clean the Cache/Dalvik and reboot to the system. I assume that you just finished the point 5 on the subsection above. 
1. When the installation of the Gapps finishes, tab `Wipe Cache/Dalvik`, and swipe to Wipe.
2. Reboot the System

It takes quite a lot of time, while you just see the `android` start screen (wite/grey waving).

Now it's time for the system setup, as a happy new tablet user ;-)