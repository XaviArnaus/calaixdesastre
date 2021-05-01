

# Install ADB & Fastboot in Mac
1. Open a terminal
2. Run: `brew install android-platform-tools`


# Install TWRP
Download the TWRP for Tilapia (Nexus 7 3G) from https://dl.twrp.me/tilapia/twrp-3.5.2_9-0-tilapia.img.html (bkp: [twrp-3.5.2_9-0-tilapia.img](../../downloads/android/twrp-3.5.2_9-0-tilapia.img))

Following https://clickitornot.com/twrp-recovery-and-root-asus-nexus-7-2012-3g/

## Start Fastboot mode
1. Enable `Developer Options` by going to `About tablet` and tapping build number 7 times.
2. Enable the USB debugging on your device in `Developer Options`
3. Connect your device to the PC **using a USB data cable** (already failed once here). You should see the tablet asking for the RSA acceptance and an icon in the status bar noticing the USB debugging. 
4. NO: Hold `Volume down` and `Power`. Don't release until the Fastboot screen appears
5. NO: Open a terminal in the Mac and move to the directory that contains the downloaded TWRP image file.
4. Run: `adb reboot bootloader` -> Your device will start booting in fastboot mode 

## Unlock Fastboot
My Nexus 7 had the Fastboot locked. At the bottom of the Fastboot info appears `LOCK STATE - LOCKED` in red.
Following https://www.technorms.com/27360/how-to-lock-unlock-nexus-7-bootloader

1. Run: `fastboot oem unlock`. Appears an explanation about why you shouldn't unlock and install a custom OS. Also tells that **all data will be lost**
2. Press the `Power` button to unlock. In the Mac terminal appears some messages:
```
(bootloader) erasing userdata...
(bootloader) erasing userdata done
(bootloader) erasing cache...
(bootloader) erasing cache done
(bootloader) unlocking...
(bootloader) Bootloader is unlocked now.
OKAY [ 34.782s]
Finished. Total time: 34.783s
```

At the bottom of the Fastboot info appears `LOCK STATE - UNLOCKED` in red.

## Flash TWRP image
1. Rename the image to `TWRP.img`
2. Run: `fastboot flash recovery TWRP.img`
```
Sending 'recovery' (10816 KB)                      OKAY [  1.363s]
Writing 'recovery'                                 OKAY [  0.492s]
Finished. Total time: 1.942s
```
3. Press `Volume Up` or `Volume Down` to reach the `Recovery Mode` and press `Power` to accept. The TWRP screen should appear.

In my case it didn't. Appeared an Android toy with a red exclamation mark. 
* I restarted the tablet by long pressing the `Power` button
* A "brand new installation" appeared, asking for a password.
* I restarted the tablet into Fastboot by long pressing `Volume Down` and `Power`.
* I re-flashed without formatting the user data.
* I pressed `Volume Up` or `Volume Down` to reach the `Recovery Mode` and press `Power` to accept. 
* The TWRP screen appeared.

4. Swipe the bar to unlock TWRP
5. Swipe the bar again to Allow modifications without checking any checkbox.
6. Tab `Wipe`
7. Tab `Format Data`. Otherwise the further Factory Reset fail. You'll be asked to type `yes` to continue. **This destroys all data**