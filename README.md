![Not my Mac but whatever](https://macfinder.co.uk/wp-content/uploads/2019/06/img-Mac-Pro-06042.jpg)
# ctaetcsh's HaccMac Files
Files related to my Hackintosh project.
It is a direct clone from my EFI folder and is mainly used as a resource in case I need to revert to a previous version of my bootloader files, or if somebody else would like to use them.
**Please see the config.plist warning before using it in your own system.** I cannot stress this enough. *Do not use somebody elses config.plist.*

## Some files were removed/edited!
The entire audio folder under resources was removed as GitHub probably dont want to store that.
In addition, the config.plist was edited. Reason below. V

## Changes made for privacy
Certain files, like the config.plist, were modified before upload for my privacy. If you do intend to use any file, double check it before using it. **Read the f@#king config.plist warning!**

## Current Status of build: Silver
I kinda got lucky with my part selection, and most things did work out in my favor, however, this build is not golden as there are still various issues that have not been fixed as of yet.

### Graphical Summary (TL;DR)

Hardware | Compatibility Rating
-------- | --------------------
Booting | Golden
Graphics | Silver+
Wi-Fi/BT | Golden
Onboard Audio | Golden
Sleep/Wake | Silver++

IService | Compatibility Rating
-------- | --------------------
iCloud | Silver+
iCloud Drive | Golden
iCloud Photos | Golden
Mail, Contacts, Calendar | Golden
Find my Mac | Silver 
Keychain | Silver
iMessage | Dirt (Broken)
FaceTime | Dirt (Broken)
App Store | Golden
Apple Music | Golden


### What is working

* No input, graphical booting. Verbose mode is disabled (unadvised) and OpenCanopy installed successfully. The system boots fine however macOS is the only OS installed on this computer.
* Graphics worked perfectly once the OS was installed. I am using an RX 480 which is natively supported in macOS Catalina and it works without issue. Important: See note #1.
* WiFi works perfectly and supports AirDrop. I am using a TP-Link Archer T9e which uses a Broadcom chipset, which is the only chipset vendor supported by macOS. See note #2.
* Onboard Audio worked fine when AppleALC was installed and configured, it did take a bit to get it working, but it works fine nonetheless.
* I have not tested the onboard Ethernet controller under macOS yet, but I the Kext is installed and it does show up correctly in macOS, with no tinkering required.

Note #1: I am using a VisionTek RX 480, **which is listed as unrecommended on the Dortania GPU buyers guide,** as some people have reported issues with it. I have not encountered any huge GPU problems so far, with the exception of DRM which I will elaborate later.

Note #2: In order to get AirDrop working you do need a Bluetooh card/adapter in your system as well to scan for devices. Without this, AirDrop is a fish out of water without Bluetooth.

### What is kinda working

* DRM content has been hit-or-miss for me. The FairPlay 1 test on the Dortania DRM troubleshooting page does not play under QuickTime. Amazon Prime Video does not play under Safari but works under Chrome(ium) so it might be an issue with Safari.
* Sleep/Wake functionality is again, hit-or-miss. It is functional with my system, however waking from sleep causes weird issues with mouse movement so I elected to keep it off and just have the monitor got to sleep instead. This might be specific to me though as I am using a wireless Logitech G603, which may be the reason for the odd mouse movement. (yes I did replace the batteries)

### What is not working

* IMessage refuses to work, even after trying many different serials and doing the steps in the troubleshooting guide. This does kinda suck but is probably down to something with my configuration, which I will need to troubleshoot later.
* Siri does not work, which may be related to Microphone input on Zen processors being questionable at the moment, dispite me using a USB headset which is unrelated to the Zen Microphone issues.

### Software Specific Issues

* Discord has an issue where joining a Voice Call will cause it to crash then loadloop as it automatically reconnects. There is a patch for this, however it is NOT permanent. Fixing this issue will likely require patching the Discord executable. (Really you just need to put some debug info in front of the app string and it will work, wtf Discord).

## Contacting Me
If you notice something that needs to be fixed or if you have some questions, there a couple ways to get in touch:

* Discord is the fastest method as I am there quite often. You can add me at ctaetcsh#7777.
    * Only contact me in relation to this repo or a build with similar hardware. Do not bug me with step by step instructions or help with builds, refer to the documentation below.
* You can also file an issue or pull request if there is a clear issue I missed. All the files were ran through the OpenCore sanity checker but it doesn't hurt to go over some things.

## Other things to read

* If for whatever reason you are going to use files from this repo, PLEASE read the config.plist warning. It contains VITAL information about using these files.
    * File: config_plist_warning.md
* If you are looking to make a build for yourself, refer to documentation below. It's far better then this.
    * Dortania Anti-Buyers Guide (if your hardware is in here, don't hackintosh): [Link](https://dortania.github.io/Anti-Hackintosh-Buyers-Guide/)
    * Opencore Installation Guide (desktop): [Link](https://dortania.github.io/OpenCore-Desktop-Guide/)
    * OpenCore Troubleshooting Guide: [Link](https://dortania.github.io/OpenCore-Desktop-Guide/troubleshooting/troubleshooting.html)
    * AMD OS X Community (For Ryzen builds, techincal support & discussion): [Link](https://amd-osx.com)
    

#### Congradulations! You reached the end!

Wow, you read all of that? Good job, and good on ya. A requirement for undertaking this project is undoubtably the ability to fully read documentation and understand what it's saying. **If you just scrolled to the end then go away this praise isn't for you.**