# Nexus 7 2012 3G (tilapia) as a Spotify box
This is a log of actions to end up with a 7-inches tablet that runs basically the Spotify app, meant to connect to any Bluetooth speaker box and then free my private phone.

## Why a Nexus 7
I was looking for a 7-inches tablet, which I think is the best compromise between size and portability for something simple as this project.
I always liked the Nexus 7, even I am aware that the first generation was quite awful in specs.
I found a quite cheap unit in the second hand market, enough for give this project a try.

## Project requirements:
* 7-inches tablet
* Bluetooth
* 3G/LTE support (internet via SIM card)
* Fast enough to move through the system without getting too frustrated.

## Nexus 7 2012 out-of-the-box issue
The first generation (2012) is widely known poor in specs, which makes it cheap. Just getting the unit, restoring factory defaults and apply the updates, the device gets slow as hell and unusable. Flashing a ROM seems to be the the only option, after some time trying to workaround it playing with the settings.

## TL;TD - Final result
* Runs smooth enough to be usable and the music does not get cut
* Total lack of Google apps, single focus device.
* Satisfied with the result.

## Flash a Custom ROM
This is actually the hard work to be done. I've split the actions between:
1. Install a rich Recovery Mode to unblock the device and allow perform the Custom ROM installation
	* See [Nexus 7 2012 3G Update Recovery](nexus7-2012-3g-update-recovery.md)
2. Install the Custom ROM
	* See [Nexus 7 2012 3G Install Custom ROM](nexus7-2021-3g-install-custom-rom.md)

The following sections go beyond registering the post installation steps I applied.

## Initial setup
* Set up a WiFi
* Sim card is in.
* Set up a Google account

## Android settings
1. Sound
	* Alarm volume 0%
	* Notification volume 0%
	* Other sounds > All OFF
2. Accounts
	1. Tab on the 3 vertical dots in the top right corner
	2. Uncheck `Auto-sync data`
3. Google Play
	* For every single app:
		1. Tab the app. The app screen will open
		2. Click on the 3 vertical dots in the top right corner
		3. Uncheck `Enable auto update`
4. SIM Card
        * Deactivate SIM Pin to be asked constantly (may be a card/hardware issue)
                1. Settings > Security > Set up SIM card lock
                2. Unset `Lock SIM card`
5. Display
        * Deactivate double-tab screen wake up
                1. Settings > Display
                2. Unset `Tap to wake`

## Spotify
After the instalation, log in into your account (yeah, I'm a paying user).

In settings:
* Disable `Spotify Connect in background`
* In Notifications
	* Disable all in `Push notifications`
	* Disable all in `Email notifications`

... and download any playlist, for totally off-line moments.

## Bluetooth
Search for a speakers box or any BT audio device and connect to it.

## Wallpaper
The size for a good wallpaper is 1400x1280
