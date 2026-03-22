# Tecno-Spark 7 Pro Fuckury
### Everything you need for Tecno Spark 7 Pro. Unlock bootloader, Install GSI ROMs and Root your device! without needing a PC or Laptop

---
<br>

# Navigation
Click on each to directly jump into the topics. But follow from top to bottom and please read everything very carefully.
- [Precautions](#precautions)
- [Bootloader Unlock](#bootloader)
- [Must know about GSI](#info)
- [GSI ROM Installation](#gsi)
- [Root the Device](#mahdin)
- [Community & Support](#support)

<br>

# Precautions <a name=precautions></a>
In this section. You will find what to do before unlocking the bootloader
### Variables
- Target Phone = Your Phone, where you will unlock the bootloader 
- Host Phone = The second phone, from where you will run commands via Bugjeager

### Precautions steps
1. Login Telegram & Discord on Host Phone
2. Go to ZArchiver, create a folder called "My Backup" And inside Storage backup every necessary folders, including your images, songs, videos, etc. — Make the zip (with password) of the folder. And upload to Cloud (make sure accessiable later) or Host Phone
3. Remove every locks from your Target Phone. Fingerprint, PIN/Pattern/Password everything from Target Phone
4. Create a "Account.txt" file, and paste every Account's (Google account, Instagram account, GitHub account, etc.) informations. Like password, email, number. And send it to Host Phone
5. On Target Phone, open your "Contacts" app and go to settings. Export all contacts to the storage. Now go to any browser, open https://contacts.google.com/. Login with your main account. Click on upload and select the contacts file from the storage and upload it. Recheck if every contacts are there
6. On Target Phone, if you use Google Authenticator, for every Accounts (Facebook, Google, Instagram, etc. accounts) then turn off 2FA and MFA from the Google Account where you stored your all keys of other accounts on Google Authenticator 
7. Remove all Google accounts from the Target Phone
8. Take a screenshot of all apps — Send it to Host Phone
9. On Target Phone, remove any Tecno Account if available on settings. Like Xiaomi have Xiaomi account, Realme have Realme account on settings at Accounts or front of the settings app. Remove the Tecno account if available 
10. On Host Phone, download the GSI ROM
11. Download the Tecno Spark 7 Pro Partitions Archive on your Host Phone from [GitHub releases](https://github.com/Prime-TITAN-CameraMan/Tecno-Spark-7-Pro/releases/tag/v1.0). If your build number is different, download your firmware from [TS7Pro Firmwares](https://naijarom.com/tecno-spark-7-pro-kf8)
12. Extract the GSI ROM, you will find the `ROM.img` there. Extract the Partitions Archive or firmware and save the `boot.img`, `vbmeta.img` & `magisk_boot.img` (note Magisk patched boot image is only available on my partitions archive zip. If your build number different, you will get your magisk boot.img at rooting process]
13. Take any additional precautions if you want

---
<br> 

# Bootloader Unlock <a name=bootloader></a>
In this section, you will get guide that how to unlock the bootloader

### Variable
- Target Phone = Your Phone, where you will unlock the bootloader 
- Host Phone = The second phone, from where you will run commands via Bugjeager

### Bootloader unlock
1. Make sure to follow the [Precautions](#precautions) if you haven't yet. 
2. On Target Phone, open Settings, About Phone. Then, tap on Build Number 69 times. It will unlock Developer Options — Go to Developer Options, and turn on "USB Debugging", "Disable ADB Authorisation Timeout" and "OEM Unlock"
3. On the Host Phone, check if there's any option called "OTG Connection" in Settings, then Additional Settings. If not, skip this step
4. Open Bugjeager on Host Phone. Connect MicroUSB OTG Plug to the Host Phone and the Charging Cable Plug to Target Phone — Bugjeager should show your device click on allow
5. On the ADB section, tap on "Reboot Bootloader". Then it will ask for again, allow it. Swipe Right edge to Left edge and use click to open Fastboot section.
6. Tap on the Lightning/Cmd floating button

> **Now we are gonna run few commands to unlock the bootloader.**

1. Run this command to check if the device is successfully connected:
```
fastboot getvar all
```
If this gives lots of output about your device then proceed to the next step. If not, reconnect your Target Device with Host Device again then try again. 

2. Run this command to unlock the bootloader:
```
fastboot oem unlock
```
Then Check your Target Phone, it may show a warning screen with giving a text of "pressing volume up (or probably down) button to unlock the bootloader. If it shows volume up to unlock, tap on volume up button

3. **ONLY IF THE PREVIOUS COMMAND GAVE NO OUTPUT ON SCREEN OR GAVE ERROR**:
```
fastboot bootloader unlock
```
Then Check your Target Phone, it may show a warning screen with giving a text of "pressing volume up (or probably down) button to unlock the bootloader. If it shows volume up to unlock, tap on volume up button

4. Your device may get boot into the system after few minutes automatically. If not, run:
```
fastboot reboot
```

> **Now let's check if the phone's bootloader actually got unlocked or not**

1. If you device got reset, that means your bootloader has been unlocked. But to be sure do the following steps:
2. Open Settings, go to About Phone. Tap on "Build Number" 69 times. This will unlock your Developer Options
3. Open Settings, search or find "Developer Options", open it and check if the "OEM Unlock" can be turned off or not. Also check if the option says "bootloader is unlocked or not" 

> [!WARNING]
> If the data of the phone isn't wiped. Or, the "OEM Unlock" can be turned off. That means, your bootloader is still locked, and you have follow everything from top carefully again

---
<br>

# Must know <a name=info></a>
Before heading towards GSI installation. You must know several things about GSI ROMs and its compatibility for Tecno Spark 7 Pro

### GSI ROM Info

1. Stablity depends on the GSI ROM
2. Whatever GSI ROM you flash, they may have bugs
3. Not all GSI ROMs gonna work 
4. Some GSI ROMs can cause bootloop 

### Compatibility for Tecno Spark 7 Pro
Tecno Spark 7 Pro (Android 11) is a Troject Treble & AB slot partitions supported device. So:
1. The GSI ROM you want to install must be built for A/B partitions device. If it's for A/B partitions device, or A/B plus A-only partitions devices then you can install. If it's only for A-only slot partition device then skip that GSI ROM and find another 
2. Tecno Spark 7 Pro at its last update runs on Android 11 firmware, and Project Treble supports higher Android versions but if you jump from Android 12 to upstreamed Android 16 or 17. That would be a huge gap, which is unlikely gonna work, or may have several stability issues and even bootloop issues. If you really want to install a upstreamed Android version you must need a stable, higher fixes and backwards compatible GSI ROM just like MistOS. Yes, you can use MistOS if you want a upstreamed Android version, it is running on Android 16 QPR0, but it is a bit slower
3. Some GSI ROMs may require a bit different installation sets, which you can get from the ROM's official installation guide. Though the installation guide below is mostly gonna work on every GSI ROMs installation 

# Install GSI ROM <a name=gsi></a>
In this section, you will know how to install a GSI ROM

> [!NOTE]
> This installation process is tested with MistOS GSI ROM. You must download the [Tecno Spark 7 Pro Partitions](https://github.com/Prime-TITAN-CameraMan/Tecno-Spark-7-Pro/releases/tag/v1.0) on the Host Phone. But, If you've a different build number, download your firmware from [Here](https://naijarom.com/tecno-spark-7-pro-kf8) and extract VB Meta and boot.img from there.

### Variable
- Target Phone = Your Phone, where you will unlock the bootloader 
- Host Phone = The second phone, from where you will run commands via Bugjeager

### GSI Installation
1. Make sure to follow the [Precautions](#precautions) at first, if you haven't yet.
2. On Target Phone, open Settings, About Phone. Then, tap on Build Number 69 times. It will unlock Developer Options — Go to Developer Options, and turn on "USB Debugging", "Disable ADB Authorisation Timeout"
3. On the Host Phone, check if there's any option called "OTG Connection" in Settings, then Additional Settings. If not, skip this step
4. Open Bugjeager on Host Phone. Connect MicroUSB OTG Plug to the Host Phone and the Charging Cable Plug to Target Phone — Bugjeager should show your device allow it then it will show your device
5. On the ADB section, tap on "Reboot Bootloader". Then allow access again on Bugjeager. Swipe Right edge to Left edge and use click to open Fastboot section.

> **Commands to install the GSI ROM**

> [!WARNING]
> Before going to install a GSI ROM, I want to inform you that, **not all GSIs gonna work on the phone**. Plus try to follow the official guide of installing the GSI if available. Otherwise proceed.
Follow these process on Host Device, Bugjeager

1. Run this command to check if the device is successfully connected:
```
fastboot getvar all
```
If lot of output comes, good. Otherwise try reconnecting the Target Device with the Host Device, and try again.

2. Don't run, only type:
```
fastboot --disable-verity --disable-verification flash vbmeta
```
Now give a space and click on Attachment Icon and select the `stock_vbmeta.img` that you have saved previously and run it — If it gives error, you might made a typo mistake in spelling and gave an extra space. If it says no device, your device may got disconnected, reconnect again 

3. Enter FastbootD Mode:
```
fastboot reboot fastboot
```
Bugjeager may show pop up again. Allow it

4. Check if your device is successfully booted into FastbootD Mode:
```
fastboot getvar is-userspace
```
If it shows nothing or error, reconnect the Target Device with Host Device, if it shows `is-userspace: yes` you are good to go to the next step. If it shows `is-userspace: no`, tru running the no.4 command again. If it still shows `is-userspace: no` then you need to flash the GSI ROM from Bootloader, which needs some refinement. If your says `is-userspace: no` then please watch [Sai Ponnamanda's Video](https://youtu.be/nbPfqLBfKSE?si=V9Fju_dr70Ax7S4i) to see what extra commands you needed to run. Otherwise if your says yes, go on:

5. Erase the system partition:
```
fastboot erase system
```
If it gives error then watch [Sai Ponnamanda's Video](https://youtu.be/nbPfqLBfKSE?si=V9Fju_dr70Ax7S4i), there you will find the exact solution for the error. Otherwise it gets success follow next step

6. Don't run, just type:
```
fastboot flash system
```
Now give a space and click on Attachment Icon and select the `<ROM-Name>.img` that you have saved previously and run it. After the command runs, it will give zero output for 5 minutes. Just wait, then `system 1/5` or `Writing System` will appear which means the ROM is being flashed. Wait until it gets completed. If you get any kind of error, check [Sai Ponnamanda's Video](https://youtu.be/nbPfqLBfKSE?si=V9Fju_dr70Ax7S4i)

7. Now Factory Reset your phone:
```
fastboot -w
``` 

8. Now reboot into your system:
```
fastboot reboot
``` 
Now wait, first boot takes 6-9 minutes. If stuck at boot logo for above 15 minutes or bootloop is happening. **If any of them is happening, please note that the GSI ROM won't work on the device, and you have to use a different one**. Check our [Support](#support) in that case.

9. If the device gets booted, setup the device.
10. Open Settings, About Phone. Then, tap on Build Number 69 times. It will unlock Developer Options — Go to Developer Options, and turn on "USB Debugging" and "Disable ADB Authorisation Timeout" 

---
<br>

# Root the device <a name=mahdin></a>
In this section, you will find out how to root your device

### Variables
- Target Phone = Your Phone, where you will unlock the bootloader 
- Host Phone = The second phone, from where you will run commands via Bugjeager

### Root the device
1. Make sure on Target Phone, in Developer Options, "USB Debugging" and "Disable ADB Authorisation Timeout" are turned on. And, on Host Phone, check if there's any option called "OTG Connection" in Settings, then Additional Settings. If not, skip this step.
2. On Target Phone and Host Phone, Download Magisk from [Official GitHub Repository](https://github.com/topjohnwu/Magisk/releases/download/v30.7/Magisk-v30.7.apk) and install it. Also, open it one time and then close it
3. Now from my Tecno Spark 7 Pro Partitions Archive zip, get the `magisk_boot.img`.

<details>
  <summary>If you have different build number and can't the one I provided</summary>

On Host Device
1. Download your firmware from [Here](https://naijarom.com/tecno-spark-7-pro-kf8)
2. Extract the zip
3. Extract `boot.img` from there
4. Open Magisk, click on "Install" the top one
5. Click on "Select and patch a file" 
6. It will redirect you to your filesystem. Find your `boot.img` there
7. Tap on the `boot.img`
8. It will bring you back to Magisk, then click on "LET'S GO". Let it be done
9. You will get Magisk patched boot.img in `Internal Storage/Download/`. That's your Magisk rooted `boot.img`, keep it
</details>

4. Open Bugjeager on Host Phone. Connect MicroUSB OTG Plug to the Host Phone and the Charging Cable Plug to Target Phone — Bugjeager should show your device codename, allow it
5. On Host Phone, Bugjeager. On the ADB section, tap on "Reboot Bootloader". Then swipe Right edge to Left edge and go to Fastboot section, then click on floating icon to open cmd.

> Now time to run few commands to root your device

1. Check if the device got connected:
```
fastboot getvar all
```
If lot of output comes, good. Otherwise try reconnecting the Target Device with the Host Device, and try again.

2. Check if your device supports A/B slot:
```
fastboot getvar has-slot:boot
```
**If the output is yes:**
  - Don't run, only type:
```
fastboot flash boot_a
```
Now give a space and click on Attachment Icon and select the `magisk_boot.img` that you have saved previously and run it — If command success, go on. If not, try checking the spelling and spaces are correct or not.
  - After that, don't run. Only type:
```
fastboot flash boot_b
```
Now give a space and click on Attachment Icon and select the `magisk_boot.img` that you have saved previously and run it — If command success, go on. If not, try checking the spelling and spaces are correct or not.

**If the output is no:**
  - Don't run, only type:
```
fastboot flash boot
```
Now give a space and click on Attachment Icon and select the `magisk_boot.img` that you have saved previously and run it — If command success, go on. If not, try checking the spelling and spaces are correct or not.

3. Run `fastboot reboot` — If the device is stuck at boot logo above 9 minutes, or causing bootloop. You may have flashed wrong `boot.img`. In that case, come on our [Support group](#support)
4. If successfully booted, open Magisk. After that, if Magisk says "Additional Step Required", click on it and let it be done. It may ask to reboot the phone again, do it.
5. You are successfully rooted!

#### Congratulations everything is done
If you got any error, trouble, issue check [Support](#support)

---
<br>

# Community & Support <a name=support></a>
If you get any trouble. Or, wants to get real-time support. Or, wants to talk and get suggestions. Or, anything else. Join our community & support group 

## [Tecno Spark 7 Pro | Support](https://t.me/TecnoSpark7Pro1)
