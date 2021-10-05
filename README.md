<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [Android Tablet Setup Guide](#android-tablet-setup-guide)
  - [Hardware Requirements](#hardware-requirements)
    - [Android Tablet](#android-tablet)
    - [Keyboard](#keyboard)
      - [Portable/Stationary Keyboards](#portablestationary-keyboards)
      - [Stationary Keyboards](#stationary-keyboards)
      - [Portable Keyboards](#portable-keyboards)
    - [Mouse](#mouse)
    - [USB-C Hub](#usb-c-hub)
    - [Power Adapter](#power-adapter)
    - [KVM Switch](#kvm-switch)
    - [Stand](#stand)
    - [Game Controller](#game-controller)
  - [Android OS and Applications Setup](#android-os-and-applications-setup)
    - [Initial Setup](#initial-setup)
    - [Disabling Vendor Extensions](#disabling-vendor-extensions)
      - [Samsung S7+ and Other Samsung Tablets](#samsung-s7-and-other-samsung-tablets)
      - [Other Vendor Tablets](#other-vendor-tablets)
    - [Optional Settings](#optional-settings)
    - [Browser Setup](#browser-setup)
    - [Email Client Setup](#email-client-setup)
  - [Tips and Tricks for Using Android](#tips-and-tricks-for-using-android)
  - [Installing Termux](#installing-termux)
  - [Termux LXQT Native Desktop Setup](#termux-lxqt-native-desktop-setup)
  - [Ubuntu KDE proot-distro Desktop Setup](#ubuntu-kde-proot-distro-desktop-setup)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Android Tablet Setup Guide

This document aims to guide you in setting up your Android tablet as a useful and powerful computing device rather than a novelty toy. I will show you how to disable a lot of annoyances, install the best web browser, email client and a linux desktop. Some annoyances will remain, due to the nature of Android, but you will quickly get used to them and they won't interfere with your workflow.

Rooting your device or flashing a different distribution of Android is not necessary for the purposes of this setup. You will need to turn on developer mode and do some things with `adb` however.

There are many advantages to this setup. You will have an ARM device with incomparably better battery life than a laptop, while having almost the full power of a linux laptop, as well as full access to all mobile apps without having to switch to a different device.

This guide is very opinionated, these are my personal preferences, feel free to make your own choices about the details of setup as long as you understand what you are doing.

I am using Android 11, previous versions will not have all the features described here, if you are using one you will need to make any necessary adjustments.

### Hardware Requirements

I am assuming for the purposes of this setup, that you are using a mid-range to high-end Android tablet with plenty of RAM and storage, with a keyboard and bluetooth mouse.

#### Android Tablet

I am using the Samsung S7+ tablet with the keyboard cover case, this is currently the most powerful tablet on the market. But any mid-range tablet will work for this purpopse as well.

If you are buying a tablet, I recommend getting one with plenty of internal storage or an SD card slot. If internal storage is small, but you have an SD card slot, also buy a high capacity SD card and format it as internal storage. The bigger the better, especially if you will do development.

Make sure the tablet uses a USB-C port and **NOT** micro-usb. If your tablet uses micro-usb, you will still be able to follow this setup with a bluetooth keyboard and mouse, but you will not be able to connect USB devices with an OTG adapter and charge the tablet simultaneously. With a USB-C hub however, this is possible.

Make sure to get a case with a kickstand.

#### Keyboard

While you can connect any wired or wireless keyboard with a USB-C hub, a bluetooth keyboard is more practical, especially for portable use. The Samsung S7+ keyhboard cover case is adequate for portable use, but I would recommend a better keyboard for stationary use.

Some good options for a bluetooth keyboard:

##### Portable/Stationary Keyboards

**Razer BlackWidow V3 Mini HyperSpeed Wireless Mechanical**

https://www.amazon.com/Razer-BlackWidow-HyperSpeed-Wireless-Mechanical/dp/B0935JBWTN/

This is the best choice for both portable and stationary use, the keyboard feels wonderful to type on and is small enough to put in your backpack. You will probably want to get a wrist-rest for it.

**Keychron K7 and K3 Ultra-slim Wireless**

K7:

https://www.keychron.com/products/keychron-k7-ultra-slim-wireless-mechanical-keyboard?variant=39396239016025

K3:

https://www.keychron.com/products/keychron-k3-wireless-mechanical-keyboard?utm_source=navi%20to%20K3&utm_medium=navi%20bar&utm_campaign=navi%20to%20K3

These mechanical keyboards have excellent reviews, and they are more portable than the Razer above, while still being nice to type on.

##### Stationary Keyboards

You can get a great full-size bluetooth keyboard:

**GameSir GK300 Wireless Mechanical Gaming Keyboard**

https://www.amazon.com/gp/product/B07PXJC64S/

I recommend getting a better wrist-rest than the one it comes with.

For stationary use, you can also connect any wired or wireless keyboard with a USB-C hub (see below about USB-C hubs). I personally like the Corsair K70 MK.2 with blue switches as far as wired keyboards go, and the Unicomp keyboards.

Corsair K70:

https://www.corsair.com/us/en/Categories/Products/Gaming-Keyboards/RGB-Mechanical-Gaming-Keyboards/K70-RGB-MK-2/p/CH-9109011-NA

Unicomp Ultra Classic:

https://www.pckeyboard.com/page/product/00UA41P4A

Unicomp EnduraPro (with trackpoint mouse device, currently unavailable):

https://www.pckeyboard.com/page/category/EnduraPro

There are of course a huge number of other excellent keyboards available.

##### Portable Keyboards

The best reviewed ultra-portable keyboard available right now:

**Microsoft Designer Compact Keyboard**

https://www.amazon.com/Microsoft-Designer-Compact-Keyboard-21Y-00031/dp/B08JM45NSM/

Any portable bluetooth keyboard will work, but avoid mini-keyboards that are missing many standard keyboard keys.

#### Mouse

You can use any mouse, wired or wireless with a USB-C hub, but I recommend a bluetooth mouse. Any bluetooth mouse will work, I recommend this one for both portable and stationary use:

**Logitech MX Anywhere 3**

https://www.amazon.com/Logitech-Performance-Scrolling-Customizable-Bluetooth/dp/B089NJQR5T/

When buying a mouse, keep in mind that extra features like programmable buttons will not work on Android. But the standard 3 buttons, scroll wheel, side scrolling and back/forward buttons will all work fine.

#### USB-C Hub

For connecting USB devices such as a keyboard, mouse, etc., get any USB-C hub with power delivery. This is necessary to be able to charge your tablet while using USB devices. 100 Watt power delivery is preferrable to use the power adapter I mention below.

#### Power Adapter

I recommend getting a USB-C power adapter that supports power delivery, instead of the standard charger. This is also necessary to use the KVM switch I mention below.

I recommend this one:

**Nekteck 95W USB C Wall Charger with Multiple Ports**

https://www.amazon.com/Nekteck-Multiple-Plodable-Compatible-ThinkPad/dp/B085RHFR5S/

This one also has a couple of USB ports to charge your phone or other devices.

#### KVM Switch

You can use a USB-C KVM with power delivery to switch USB peripherals such as a keyboard and mouse and other devices between your tablet and other computer, laptop or desktop. For this you will need a power adapter that supports power delivery, like the one above. This KVM is excellent for this purpose:

**IOGEAR - Access Pro 2-Port USB-C KVM Switch with Power Delivery**

https://www.amazon.com/IOGEAR-Access-Delivery-Compliant-GUD3C04/dp/B07WRN3FZN/

For the power delivery function to work, your tablet has to be connected to port 1.

#### Stand

I recommend getting a monitor stand about 4 inches high or so for your tablet, I have this one:

https://www.allsop.com/product/redmond-monitor-stand-14-inch-wide-platform-29248/

#### Game Controller

Most Android games do not work with a mouse and keyboard. A few work to a degree but are unplayable. A few have good support. Most games, however, work with a game controller. And the standard and most compatible type of game controller is an Xbox controller or Xbox compatible controller. And since the newest Xbox controllers have bluetooth and are excellent, you might as well get the real thing:

**Xbox Wireless Controller**

https://www.amazon.com/dp/B07GHWHFR5/

### Android OS and Applications Setup

#### Initial Setup

1. Factory reset your tablet. Even if you just got it, doing a factory reset will put it in a cleaner state. Backup any data you need first, and then go to `Settings -> General Management -> Reset -> Factory data reset`.

2. Follow the prompts on the device for initial setup. Login to your Google account. **DO NOT** restore apps and settings from your Google account, you want a clean state not all the garbage that is on your phone.

3. Go to `Settings -> Display` and turn on `Dark Mode`. If your version of Android does not have dark mode, I do not recommend using a dark mode app, those do not work very well, just turn on dark mode in your apps individually.

4. Go to `Settings -> Display -> Screen Timeout` set to 10 minutes.

5. Install your favorite launcher, I recommend Smart Launcher, many people like Nova and Lawnchair.

6. Install Rotation Control by CrapeMyrtle from the Play store. Open the app and turn on `Start controlling` and `Start on boot`. From the notification area tap the landscape lock button which looks like this:

```
  ******
 \|/   *
-----------
|         |
|         |
-----------
  *    /|\
  *******
```

7. Go to `Settings -> Lock Screen -> Screen Lock Type` set to none.

8. Go to `Settings -> Display`. Turn off edge panels. Go to `Navigation Bar` and turn on swipe gestures, turn off gesture hints and turn off show button to hide keyboard. Click `More Options` to see a description of the gestures.

9. Go to `Settings -> Display`, turn off adaptive brightness and eye comfort sheild. Set the brightness to a comfortable level that is not too high.

10. Go to `Settings -> Advanced Features`. Turn off everything, especially game launcher and daily board. Go to `Side Key` and turn off double press, set press and hold to power off menu.

11. Hold the weather notifaction and disable the `current weather conditions` category, click save. Install your favorite weather app such as 1Weather. When you see a notification from the built-in `Weather` app, turn off that notification category as well.

12. Go to `Settings -> About Tablet -> Software Information` tab `Build Number` 7 times to turn developer mode.

13. Go to `Settings -> Developer Options` and turn on USB debugging.

14. Install SystemUI Tuner by Zachary Wander. You will need to connect your tablet to a computer for the setup, follow the instructions to install android platform tools and grant the necessary permissions.

15. Once you have successfully set up SystemUI Tuner, open it and go to `UI -> Immersive Mode`, check the checkbox under `All Apps` and `Full` and click OK.

16. Install External Keyboard Helper Pro by Apedroid. Go to `Settings -> General Management -> Keyboard List and Default` and turn on External Keyboard Helper Pro. Go to `Settings -> General Management -> Physical Keyboard -> External Keyboard Helper Pro` and select your layout such as `English (US) Qwerty Style`. On Samsung tablets and possibly others you will also need to turn off the Samsung keyboard software for this app to work, see the [Disabling Vendor Extensions](#disabling-vendor-extensions) section for instructions on how to do that. See the [Optional Settings](#optional-settings) section for how to map CapsLock to Control.

17. Go to `Settings -> General Management -> Physical Keyboard -> Change Language Shortcut` turn off everything except control + space.

18. Install F-Droid from https://www.f-droid.org/ .

#### Disabling Vendor Extensions

First, install Apk Analyzer by Martin Styk.

##### Samsung S7+ and Other Samsung Tablets

For the Samsung S7+ and possibly other Samsung tablets, run the following commands using the Android platform tools `adb` executable you installed when setting up SystemUI Tuner:

```powershell
./adb shell pm disable-user --user 0 com.samsung.android.honeyboard

./adb shell pm disable-user --user 0 com.samsung.android.svoiceime

./adb shell pm disable-user --user 0 com.samsung.android.game.gametools
```
.

This will disable the Samsung keyboards allowing Extenral Keyboard Helper Pro to work, as well as the incredibly annoying game optimizer extension.

##### Other Vendor Tablets

You will have to do some experimentation to determine which vendor software to disable. Disabling some apps can break parts of the system, like sections of Settings, and it may be better to turn them off by other means, using a Settings configuration, turning off the notifications, etc..

When you have identified which vendor software is causing you problems, open Apk Analyzer and find the package name, which is the line under the name of the app, for example on my tablet the package name for Samsung Keyboard is com.samsung.android.honeyboard.

To disable this software, use the `adb` binary from Android platform tools that you installed when setting up SystemUI Tuner, and execute the following command:

```powershell
./adb shell pm disable-user --user 0 <package-name>
```
.

If doing this causes something to break on your system, run the following command to re-enable the software:

```powershell
./adb shell pm enable <package-name>
```
.

Then try to disable the software by other means, e.g. a Settings configuration or notifications block.

#### Optional Settings

1. To set your time format to 24-hour and your time zone to GMT, go to `Settings -> General Management -> Date and Time`, turn off automatic time zone, turn on use 24-hour format. Go to `Time Zone -> Region` and select Iceland.

2. If you want to use a calendar service to remind you of your appointments etc., install Google Calendar.

3. For a PDF viewer app, install Adobe Acrobat Reader.

4. If you want to map CapsLock to Control or remap any other keys on your keyboard using Extenral Keyboard Helper Pro, follow the following steps. Go to `EKH Settings -> Advanced Settings -> Keyboard Mapping` and enable override special keys. Click `Customize Keyboard Mappings` and start a new custom layout called `Custom 1`. Click `Add New Key Mapping`. To map CapsLock to Control, click Keycode select Left Control, click the Change button and press CapsLock, it should display scancode 58. Click Save.

#### Browser Setup

1. Go to `Settings -> Apps -> Chrome -> Install Unknown Apps` select `Allow From This Source`.

2. Open Chrome and go to https://github.com/kiwibrowser/src.next/releases and install the latest dev arm64 apk.

3. Go to `Settings -> Apps -> Kiwi Browser -> Install Unknown Apps` select `Allow From This Source`.

4. Open Kiwi, go to `Settings -> Accessibility` select `Desktop mode by default`.

5. Install your favorite chrome extensions from the chrome web store, such as uBlock Origin, I also like Night Eye for dark mode on web sites.

6. Go to `Settings -> Apps -> YouTube -> Set as Default -> Open Supported Links` and choose `in other app`.

#### Email Client Setup

1. Go to `Settings -> Apps -> Gmail` on the bottom tap disable.

2. Install Nine - Email & Calendar by 9Folders Inc.. Go through the initial setup to set up your account.

3. On the left pane, go to `Settings -> Account Settings -> Signature -> Manage Signatures -> Default Signature` delete the text and click save.

4. Go to `Settings -> VIP -> Notification` turn on silent notification and turn off LED light.

5. If you do not get a lot of spam, go to `Settings -> Security -> Load Remote Images` and choose always display. Otherwise, you can whitelist sender images when you open an email.

6. Go to `Settings -> Account -> Sync Schedule -> Sync Frequency` and set to every 5 minutes, also turn on auto sync data and sync when roaming.

### Tips and Tricks for Using Android

When you get any unwanted notifications, you can hold the notification and turn off the notification category or all notifications from that app.

For some services, it is better to just use the website in Kiwi instead of the mobile app. For example, the Yelp app is terrible, and I just use the website.

If you are a Discord user, I recommend against the Android app, just run discord in Kiwi or Chromium (see the [Ubuntu KDE proot-distro Desktop Setup](#ubuntu-kde-proot-distro-desktop-setup) section for how to set up Chromium.)

Here are some essential keyboard shortcuts for Android:

| Keyboard Shortcut | Action                                  |
|-------------------|-----------------------------------------|
| ctrl + esc        | open menu                               |
| win + backspace   | go back                                 |
| win + enter       | go to launcher home screen              |
| alt + f4          | close app                               |
| win + tab         | show open apps overview                 |
| alt + tab         | switch to next app                      |
| shift + alt + tab | switch to previous app                  |
| ctrl + alt + del  | reboot instantly                        |

In the overview screen, you can move an app up to close it, or down to switch to it.

If you enabled immersive mode with SystemUI Tuner as per this guide, the home gesture will require swiping up from the bottom twice. But it's easier to just press win + enter on the keyboard.

### Installing Termux

1. Install Termux and Termux:Styling from F-Droid.

2. In Termux, run these commands:

```bash
pkg in -y unstable-repo x11-repo
pkg up -y
pkg in -y openssh man
termux-setup-storage
```
.

3. Install an editor of your choice for editing configuration files, if you are new to UNIX-like operating systems, install `nano`, it is simple to use. Install it with this command:

```bash
pkg in -y nano
```
.

4. Edit `~/.termux/termux.properties` and set the following:

```
extra-keys = []
bell-character = ignore
back-key = escape
```
.

5. Go to `Settings -> Apps -> Termux` and make sure that `Allow Background Activity` is turned **ON** and `Battery Optimization` is turned **OFF**.

6. Go to `Settings -> Apps -> Termux -> Appear on Top` and turn on allow permission.

7. To set up a Linux desktop, you can follow either of the next two sections, or both, they do not conflict. If you set up both, you will be able to run either and use Chromium from the Termux native desktop.

### Termux LXQT Native Desktop Setup

1. Install TruVNC Secured Vnc Client Pro.

2. Go to `Settings -> Apps -> TruVnc` and make sure that `Allow Background Activity` is turned **ON** and `Battery Optimization` is turned **OFF**.

### Ubuntu KDE proot-distro Desktop Setup

1. Install TruVNC Secured Vnc Client Pro.

2. Go to `Settings -> Apps -> TruVnc` and make sure that `Allow Background Activity` is turned **ON** and `Battery Optimization` is turned **OFF**.
