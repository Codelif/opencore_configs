# OpenCore Configurations for HP Slimline 450-010il Desktop PC
There are my configurations which are working. 

## Tested macOS Versions
* 10.13.x (High Sierra)
* 10.14.x (Mojave)
* 10.15.x (Catalina)
* 11.5.x (Big Sur)
* 12.0 (Monterey) (**NOT WORKING**)

## Specs
### HP Slimline 450-010il Desktop PC
* Motherboard: Memphis2-S
* CPU: Intel Core i3-4170
* GPU: Intel HD Graphics 4400
* Audio Codec: ALC659-CG
* Ethernet: Realtek RTL8151GH-CG
* WiFi & Bluetooth: BCM943142
* Storage: WDC WD10EZEX-60M2NA0 HDD 1TB

[Spec Sheet](https://support.hp.com/id-en/document/c04717162)
### Changes to Hardware
* 10 GB RAM (Dual channel running at 1600 MHz)(2GB, 8GB)
* Disconnected WiFi and Bluetooth Card

## Bootloader
OpenCore 0.7.7
### AppleALC
At the time of writing, ALC659 codec is not in the supported [list](https://github.com/acidanthera/AppleALC/wiki/Supported-codecs) of [AppleALC](https://github.com/acidanthera/AppleALC).\
But worry not as ALC662 will work just fine. This codec is also used by ALSA in linux for this machine.
#### My Results:
ALC662 layout-id: `0x100101, 0x100300, layout 5, 7, 11, 12, 13, 15, 16, 17, 18, 19, 66`

Not Working: 7\
Identified but not Working: 5, 11, 12\
Working: 13

Rest are not tested.

## Status Report
### What is not working.
* WiFi
* Bluetooth (May run but I have not tried fixing)
* VGA (duh)
### What is buggy.
* Sleep mode (doesn't even wake up in 10.13.x)
* Display wake up (takes 2-5 seconds to startup properly)
* .jpg cannot be viewed in Preview (Doesn't work in 10.14, 10.15, 11) (Works in 10.13)
* Adobe Premiere Pro opens but playing video doesn't work. (Probably a graphics issue)


## Note for macOS 11 Big Sur
While installing, there were a few of problems I have faced that I want to bring light to:
* Online Installer does not work for some reason.
* In Offline Installer, the installer reboot at 12 minutes. This is nothing to worry about. After reboot, you will find "macOS Installer" in boot menu.
* In "macOS Installer", it may reboot several times but keep booting to it until it disappears and you find your Big Sur drive in boot menu.
* Same as in "macOS Installer", you will find that Big Sur drive will reboot several times. Keep rebooting until it goes to macOS setup.


