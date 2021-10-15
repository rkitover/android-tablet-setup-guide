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
    - [Audio Interface](#audio-interface)
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
    - [LXQT Installation](#lxqt-installation)
    - [LXQT Configuration](#lxqt-configuration)
    - [QTerminal Configuration](#qterminal-configuration)
  - [Ubuntu KDE proot-distro Desktop Setup](#ubuntu-kde-proot-distro-desktop-setup)
    - [Ubuntu KDE Installation](#ubuntu-kde-installation)
    - [KDE Configuration](#kde-configuration)
    - [Terminator Terminal Configuration](#terminator-terminal-configuration)
    - [Optional KDE Configuration](#optional-kde-configuration)
    - [Chromium Browser Installation](#chromium-browser-installation)
  - [Kiwi Browser Launcher Configuration](#kiwi-browser-launcher-configuration)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Android Tablet Setup Guide

This document aims to guide you in setting up your Android tablet as a useful and powerful computing device rather than an expensive toy. I will show you how to disable a lot of annoyances, install the best web browser, email client and a linux desktop. Some annoyances will remain, due to the nature of Android, but you will quickly get used to them and they won't interfere with your workflow.

Rooting your device or flashing a different distribution of Android is not necessary for the purposes of this setup. You will need to turn on developer mode and do some things with `adb` however.

If your device supports this, and you do want to flash a community Android distribution, there are many choices available, the most popular being LineageOS. This will also give you root.

If you want to root your device and a method is available, you will gain additional capabilities such as backups and access to additional Termux software. Most people do not need this these days.

You should also be aware that on some devices such as Samsung ones, rooting or flashing a different firmware will void your warranty.

There are many advantages to this setup. You will have an ARM device with incomparably better battery life than a laptop, while having almost the full power of a linux laptop, as well as full access to all mobile apps without having to switch to a different device.

This guide is very opinionated, these are my personal preferences, feel free to make your own choices about the details of setup as long as you understand what you are doing.

I am using Android 11 on a Samsung tablet, previous versions and other vendor distributions will not have all the features described here in the same places described here, if you are using such a device you will need to make any necessary adjustments.

This setup will also work with other Android devices that you use with a keyboard and mouse/trackball, such as PC and Raspberry Pi versions of Android and Android TV devices such as the NVIDIA SHIELD. Some phones, such as ones made by Samsung, can also output video through a USB-C hub or adapter, and along with a bluetooth mouse and keyboard you would be able to follow this setup with such a configuration. Using a Linux graphical desktop on a tiny phone screen with a touch keyboard is not practical however.

If you have any issues with these instructions or configuration code, feel free to open an issue on the GitHub project page, or send me corrections and additions via pull request.

### Hardware Requirements

I am assuming for the purposes of this setup, that you are using a mid-range to high-end Android tablet with plenty of RAM and storage, with a keyboard and bluetooth mouse.

#### Android Tablet

I am using the Samsung S7+ tablet with the keyboard cover case, this is currently the most powerful tablet on the market. But any mid-range tablet will work for this purpose as well.

If you are buying a tablet, I recommend getting one with plenty of internal storage or an SD card slot. If internal storage is small, but you have an SD card slot, also buy a fast and high capacity SD card and format it as internal storage. The bigger the better, especially if you will do development.

Make sure the tablet uses a USB-C port and **NOT** micro-USB. If your tablet uses micro-USB, you will still be able to follow this setup with a bluetooth keyboard and mouse, but you will not be able to connect USB devices with an OTG adapter and charge the tablet simultaneously. With a USB-C hub however, this is possible.

Make sure to get a case with a kickstand.

#### Keyboard

While you can connect any wired or wireless keyboard with a USB-C hub, a bluetooth keyboard is more practical, especially for portable use. The Samsung S7+ keyboard cover case is adequate for portable use, but I would recommend a better keyboard for stationary use.

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
.

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
.

Any portable bluetooth keyboard will work, but avoid mini-keyboards that are missing many standard keyboard keys.

#### Mouse

You can use any mouse, wired or wireless with a USB-C hub, but I recommend a bluetooth mouse. Any bluetooth mouse will work, I recommend this one for both portable and stationary use:

**Logitech MX Anywhere 3**

https://www.amazon.com/Logitech-Performance-Scrolling-Customizable-Bluetooth/dp/B089NJQR5T/
.

When buying a mouse, keep in mind that extra features like programmable buttons will not work on Android. But the standard 3 buttons, scroll wheel, side scrolling and back/forward buttons will all work fine.

#### USB-C Hub

For connecting USB devices such as a keyboard, mouse, etc., get any USB-C hub with power delivery. This is necessary to be able to charge your tablet while using USB devices. 100 Watt power delivery is preferable to use the power adapter I mention below.

#### Power Adapter

I recommend getting a USB-C power adapter that supports power delivery, instead of the standard charger. This is also necessary to use the KVM switch I mention below.

I recommend this one:

**Nekteck 95W USB C Wall Charger with Multiple Ports**

https://www.amazon.com/Nekteck-Multiple-Plodable-Compatible-ThinkPad/dp/B085RHFR5S/
.

This one also has a couple of USB ports to charge your phone or other devices.

#### KVM Switch

You can use a USB-C KVM with power delivery to switch USB peripherals such as a keyboard and mouse and other devices between your tablet and laptop or desktop. For this you will need a power adapter that supports power delivery, like the one above. This KVM is excellent for this purpose:

**IOGEAR - Access Pro 2-Port USB-C KVM Switch with Power Delivery**

https://www.amazon.com/IOGEAR-Access-Delivery-Compliant-GUD3C04/dp/B07WRN3FZN/
.

For the power delivery function to work, your tablet has to be connected to port 1.

#### Stand

I recommend getting a monitor stand about 4 inches high or so for your tablet, I have this one:

https://www.allsop.com/product/redmond-monitor-stand-14-inch-wide-platform-29248/
.

#### Audio Interface

I use the FiiO BTR5 portable bluetooth DAC/amp with Etymotic IEMs.

**FiiO BTR5**

https://www.amazon.com/FiiO-BTR5-384K-Bluetooth5-0-Headphone-Unbalanced/dp/B07ZK3M6XK/

**Etymotic ER4XR**

https://www.amazon.com/Etymotic-Research-ER4XR-Extended-Response/dp/B01GW786B4/

I recommend getting a 2.5mm MMCX balanced replacement cable for the IEMs and a lanyard.

Balanced replacement cable:

https://www.amazon.com/gp/product/B07QRF4QFW/
.

Lanyard:

https://www.amazon.com/gp/product/B08D67S21Z/
.

The BTR5 is powerful enough to drive more comfortable quality on-ear headphones for extended use at home with a balanced cable. For such a pair of headphones I recommend these:

**Massdrop Sennheiser HD 6XX**

https://drop.com/buy/massdrop-sennheiser-hd6xx

Balanced cable:

https://www.amazon.com/Youkamoo-Balanced-Replacement-Compatible-Headphones/dp/B096LXP96Z/
.

However, for quality sound it is be better to connect a DAC and amp via a USB-C hub for these headphones.

**Topping E30 DAC**

https://www.amazon.com/Topping-E30-Optical-Coaxial-Desktop/dp/B0865GJLB5/

**Schiit Magni Heresy amp**

https://www.schiit.com/products/magni-1

make sure to select the heresy version.

#### Game Controller

Most Android games do not work with a mouse and keyboard. A few work to a degree but are unplayable. A few have good support. Most games, however, work with a game controller. And the standard and most compatible type of game controller is an Xbox controller or Xbox compatible controller. And since the newest Xbox controllers have bluetooth and are excellent, you might as well get the real thing:

**Xbox Wireless Controller**

https://www.amazon.com/dp/B07GHWHFR5/
.

### Android OS and Applications Setup

#### Initial Setup

1. Factory reset your tablet. Even if you just got it, doing a factory reset will put it in a cleaner state. Backup any data you need first, and then go to `Settings -> General Management -> Reset -> Factory data reset`.

2. Follow the prompts on the device for initial setup. Login to your Google account. **DO NOT** restore apps and settings from your Google account, you want a clean state not all the garbage that is on your phone.

3. Go to `Settings -> Display` and turn on `Dark Mode`. If your version of Android does not have dark mode, I do not recommend using a dark mode app, those do not work very well, just turn on dark mode in your apps individually.

4. Go to `Settings -> Display -> Screen Timeout` and set it to 10 minutes.

5. Install your favorite launcher, I use Smart Launcher, Nova and Lawnchair are very popular, and there are many good options available, here are some reviews:

https://www.tomsguide.com/round-up/best-android-launchers ,

https://www.androidcentral.com/best-android-launchers .

6. Install Rotation Control by CrapeMyrtle from the Play store. Open the app and turn on `Start Controlling` and `Start on Boot`. From the notification area, click the landscape lock button which looks like this:

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
.

Tap the lock button again when using the tablet as a tablet.

7. Go to `Settings -> Lock Screen -> Screen Lock Type` and set it to none.

8. Go to `Settings -> Display`. Turn off edge panels. Go to `Navigation Bar` and turn on swipe gestures, turn off gesture hints and turn off show button to hide keyboard. Click `More Options` to see a description of the gestures.

9. Go to `Settings -> Display`, turn off adaptive brightness and eye comfort shield. Set the brightness to a comfortable level that is not too high.

10. Go to `Settings -> Advanced Features`. Turn off everything, especially game launcher and daily board. Go to `Side Key` and turn off double press, set press and hold to power off menu.

11. Hold the weather notification and disable the `current weather conditions` category, click save. Install your favorite weather app such as 1Weather. When you see a notification from the built-in `Weather` app, turn off that notification category as well.

12. Go to `Settings -> About Tablet -> Software Information` tab `Build Number` 7 times to turn developer mode.

13. Go to `Settings -> Developer Options` and turn on USB debugging.

14. Install SystemUI Tuner by Zachary Wander. You will need to connect your tablet to a computer for the setup, follow the instructions to install android platform tools and grant the necessary permissions.

15. Once you have successfully set up SystemUI Tuner, open it and go to `UI -> Immersive Mode`, check the checkbox under `All Apps` and `Full` and click OK.

16. Install External Keyboard Helper Pro by Apedroid. Go to `Settings -> General Management -> Keyboard List and Default` and turn on External Keyboard Helper Pro. Go to `Settings -> General Management -> Physical Keyboard -> External Keyboard Helper Pro` and select your layout such as `English (US) Qwerty Style`. On Samsung tablets and possibly others you will also need to turn off the Samsung keyboard software for this app to work, see the [Disabling Vendor Extensions](#disabling-vendor-extensions) section for instructions on how to do that. See the [Optional Settings](#optional-settings) section for how to map CapsLock to Control.

17. Go to `Settings -> General Management -> Physical Keyboard -> Change Language Shortcut` turn off everything except control + space.

18. Install F-Droid from https://www.f-droid.org/ .

19. Install the apps Absolutely Nothing by SSTeam and Assist Mapper by Amir Zaidi. Go to `Settings -> Apps -> Choose Default Apps -> Digital Assistant App -> Device Assistance App` and choose Assist Mapper. Launch the Map Assist app and type "nothing" in the search field, select the Absolutely Nothing app. This fixes accidental short presses of the win key launching the assistant app, unfortunately long presses of the win key will still launch the assistant app selection setting, at least on Samsung devices, I do not yet have a solution for this.

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

This will disable the Samsung keyboards allowing External Keyboard Helper Pro to work, as well as disabling the incredibly annoying game optimizer extension.

You will need to install your favorite touch keyboard to replace the Samsung touch keyboard, such as Swiftkey. There is currently no good solution for automatically disabling an on-screen keyboard when a physical keyboard is connected, so you will have to manually switch your default keyboard from External Keyboard Helper Pro to your keyboard when using the tablet as a tablet and back in `Settings -> General Management -> Keyboard List and Default -> Default Keyboard`.

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

2. If you want to use a calendar service to remind you of your appointments etc., install Google Calendar. To use a service other than Google to sync your contacts and calendar, consider DAVx from F-Droid by https://f-droid.org/en/packages/at.bitfire.davdroid/ .

3. For a PDF viewer app, install Adobe Acrobat Reader. Document Viewer from F-Droid is also recommended by some people https://f-droid.org/en/packages/org.sufficientlysecure.viewer/ .

4. If you want to map CapsLock to Control or remap any other keys on your keyboard using External Keyboard Helper Pro, follow the following steps. Go to `EKH Settings -> Advanced Settings -> Keyboard Mapping` and enable override special keys. Click `Customize Keyboard Mappings` and start a new custom layout called `Custom 1`. Click `Add New Key Mapping`. To map CapsLock to Control, click Keycode select Left Control, click the Change button and press CapsLock, it should display scancode 58. Click Save.

#### Browser Setup

1. Go to `Settings -> Apps -> Chrome -> Install Unknown Apps` select `Allow From This Source`.

2. Open Chrome and go to https://github.com/kiwibrowser/src.next/releases and install the latest dev arm64 apk.

3. Go to `Settings -> Apps -> Kiwi Browser -> Install Unknown Apps` select `Allow From This Source`.

4. Open Kiwi, go to `Settings -> Accessibility` select `Desktop Mode by Default`.

5. Install your favorite chrome extensions from the chrome web store, such as uBlock Origin, I also like Night Eye for dark mode on web sites.

6. Go to `Settings -> Apps -> YouTube -> Set as Default -> Open Supported Links` and choose `In Other App`.

#### Email Client Setup

1. Go to `Settings -> Apps -> Gmail` and on the bottom click disable.

2. Install Nine - Email & Calendar by 9Folders Inc.. Go through the initial setup to add your account.

3. On the left pane, go to `Settings -> Account Settings -> Signature -> Manage Signatures -> Default Signature` and delete the text and then click save.

4. Go to `Settings -> General -> Message Body -> Open Links` and choose External Browser.

5. Go to `Settings -> VIP -> Notification` and turn on silent notification and turn off LED light.

6. If you do not get a lot of spam, go to `Settings -> Security -> Load Remote Images` and choose always display. Otherwise, you can whitelist sender images when you open an email.

7. Go to `Settings -> Account -> Sync Schedule -> Sync Frequency` and set to every 5 minutes, also turn on auto sync data and sync when roaming.

### Tips and Tricks for Using Android

When you get any unwanted notifications, you can hold the notification and turn off the notification category or all notifications from that app.

For some services, it is better to just use the website in Kiwi instead of the mobile app. For example, the Yelp app is terrible, and I just use the website.

If you are a Discord user, I recommend against the Android app, just run discord in Kiwi or Chromium.

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

.

In the overview screen, you can move an app up to close it, or click or slide it down to open it.

If you enabled immersive mode with SystemUI Tuner as per this guide, the home gesture will require swiping up from the bottom twice. But it's easier to just press win + enter on the keyboard.

### Installing Termux

1. Install Termux, Termux:API and Termux:Styling from F-Droid.

2. In Termux, run these commands:

```bash
pkg in -y unstable-repo x11-repo
pkg up -y
pkg in -y termux-api openssh man curl pulseaudio bash-completion
termux-setup-storage
ln -s /storage/emulated/0/Documents ~/Documents
ln -s /storage/emulated/0/Download ~/Downloads
ln -s /storage/emulated/0/Music ~/Music
ln -s /storage/emulated/0/Pictures ~/Pictures
```
.
You will be asked to grant permission to access storage to Termux, allow it.

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

5. Edit your `~/.bashrc` and add the following:

```bash
source ${TERMUX_VERSION:+/data/data/com.termux/files}/usr/share/bash-completion/bash_completion

export DISPLAY=:1

if [ -n "$TERMUX_VERSION" ]; then
    export XDG_RUNTIME_DIR=$TMPDIR
fi
```

6. Go to `Settings -> Apps -> Termux` and make sure that `Allow Background Activity` is turned on and `Battery Optimization` is turned off.

7. Go to `Settings -> Apps -> Termux -> Appear on Top` and turn on allow permission.

8. To set up a Linux desktop, you can follow either of the next two sections, or both, they do not conflict. If you set up both, you will be able to run either and use Chromium from the Termux native desktop.

### Termux LXQT Native Desktop Setup

#### LXQT Installation

1. Install TruVNC Secured Vnc Client Pro.

2. Go to `Settings -> Apps -> TruVnc` and make sure that `Allow Background Activity` is turned on and `Battery Optimization` is turned off.

3. In Termux, run:

```bash
pkg in -y tigervnc lxqt qterminal xcompmgr adwaita-icon-theme
```
.

4. Determine the native resolution of your tablet from the manufacturer specifications. For the Samsung S7+ it is 2800x1752.

5. In Termux, run `mkdikr ~/.vnc` and create the file `~/.vnc/config` with the following contents:

```
SecurityTypes=None
geometry=2800x1752
```
.

The geometry should be the one you determined in step 4.

6. Run `vncpasswd` and set your password to `termux`.

7. Create the file `~/.Xresources` containing:

```Xresources
Xft.dpi: 168
```
.

This sets the font scale to 175%, to later adjust it to a different value, multiply by 96, which is 100%.

8. Create the file `~/.vnc/xstartup` with the following contents:

```bash
#!/data/data/com.termux/files/usr/bin/sh

cd ~

if [ -n "$TERMUX_VERSION" ]; then
    export GDK_SCALE=1.75
    export GDK_DPI_SCALE=1
    export QT_SCALE_FACTOR=1.75
    export QT_FONT_DPI=96
    xrdb -merge ~/.Xresources
    xcompmgr -n &

    startlxqt
else # proot-distro
    startplasma-x11
fi
```
.

The first branch of the `if` is the Termux native desktop startup, and the second is for the following section, the proot-distro Ubuntu desktop.

The `~/.Xresources` file above and the environment variables here set the scale, `GDK_SCALE` and `QT_SCALE_FACTOR` are set to `1.75` for 175% scale, you can later adjust these as well as `~/.Xresources` to change your scale, do not modify the other variables.

9. Install Termux:Widget from F-Droid.

10. Run these commands in Termux:

```bash
mkdir -p ~/.shortcuts/tasks
cd ~/.shortcuts/tasks
touch termux-lxqt
chmod +x termux-lxqt
```
.

Put the following in the `~/.shortcuts/tasks/termux-lxqt` file:

```bash
#!/data/data/com.termux/files/usr/bin/bash

export SHELL=/data/data/com.termux/files/usr/bin/bash
source ~/.bashrc

rm -rf /data/data/com.termux/files/usr/tmp/.X1*
(
        sleep 3
        am start -a android.intent.action.VIEW -d vnc://localhost:5901/C24bit/termux >/dev/null
) &
vncserver -fg
```
.

11. Put Termux:Widget in the widget area of your launcher. The `termux-lxqt` task should appear there. Click on it to launch the LXQT desktop.

12. Adjust your scale if necessary, as per instructions above, then logout and relaunch the task.

13. After completing the following (LXQT Configuration)[#lxqt-configuration] section, follow the instructions in the [Kiwi Browser Launcher Configuration](#kiwi-browser-launcher-configuration) section. If you also complete the [Ubuntu KDE proot-distro Desktop Setup](#ubuntu-kde-proot-distro-desktop-setup) section and the [Chromium Browser Installation](#chromium-browser-installation) section, you will be able to use Chromium in LXQT.

14. After you have configured the Kiwi launcher following the [Kiwi Browser Launcher Configuration](#kiwi-browser-launcher-configuration) section, go to `Preferences -> LXQT Settings -> File Associations -> Default Applications -> Web Browser -> Change` and select Kiwi Browser.

#### LXQT Configuration

1. In LXQT, go to `Preferences -> LXQT Settings -> Appearance` and set the following:

`LXQT Theme`: Dark.

`Icons Theme`: Adwaita.

`LXQT Theme -> Font -> DPI`: set to 168 for 175% scale or a multiple of 96 (which is 100%) for your chosen scale.

Under `Widget Style` set:

| Setting     | Value        |
|-------------|--------------|
| QT Style    | kvantum-dark |
| GTK 2 Theme | Raleigh      |
| GTK 3 Theme | Adwaita      |

.

2. Right click on the panel, select `Configure Panel`. Go to `Widgets`. Remove the following if desired: desktop changer and show desktop.

3. Right click on the panel, select `Configure Panel -> Panel`, select `auto-hide`, deselect `visible thin margin`.

4. Go to `Preferences -> LXQT -> Settings -> Openbox Settings -> Mouse` and enable the following:

  - Focus Windows When the Mouse Pointer Moves Over Them,
  - Move Focus Under Mouse When Switching Desktops,
  - Move Focus Under the Mouse when the Mouse is not Moving.

5. Go to `Preferences -> LXQT Settings -> Openbox Settings -> Appearance` and deselect windows retain a border when undecorated.

6. Right click on the clock on the panel and go to `Configure "World Clock"`.

For `Time` set the following:

| Setting            | Value    |
|--------------------|----------|
| Format             | Custom   |
| Pad Hour With Zero | Select   |

For `Date` set the following:

| Setting          | Value    |
|------------------|----------|
| Position         | After    |
| Format           | Custom   |
| Show Day of Week | Select   |

#### QTerminal Configuration

1. Open QTerminal.

2. Go to `Preferences -> Appearance` and set the following:

| Setting                                    | Value             |
|--------------------------------------------|-------------------|
| Font                                       | DejaVu Sans Mono  |
| Color Scheme                               | Tango             |
| Scrollbar Position                         | No Scrollbar      |
| Application Transparency                   | 30%               |
| Show the Menu Bar                          | Deselect          |
| Hide Window Borders                        | Select            |
| Hide Tab Bar With Only One Tab             | Select            |
| Show a Border Around the Current Terminal  | Deselect          |

.

3. Go to `Preferences -> Behavior` and set the following:

|                                         |           |
|-----------------------------------------|-----------|
| History Size                            | 30000     |
| Forcefully Disable Bracketed Paste Mode | Select    |
| Trim Trailing Newlines in Pasted Text   | Select    |

.

4. Go to `Preferences -> Shortcuts` and set the following:

| Action          | Keybind                |
|-----------------|------------------------|
| Paste Selection | ctrl + alt + shift + v |
| Paste Clipboard | ctrl + alt + shift + p |
| New Tab         | ctrl + alt + shift + t |
| Next Tab        | ctrl + shift + right   |
| Previous Tab    | ctrl + shift + left    |
| Close Tab       | ctrl + alt + shift + q |

.

5. Edit the file `~/.config/openbox/rc.xml` and make the following changes:

Under `Keybindings for desktop switching`, change the key definitions as follows:

| Action            | Key         |
|-------------------|-------------|
| GoToDesktop left  | C-A-S-Left  |
| GoToDesktop right | C-A-S-Right |
| GoToDesktop up    | C-A-S-Up    |
| GoToDesktop down  | C-A-S-Down  |
| ToggleShowDesktop | C-A-d       |

.

Under `Keybindings for windows` set the key for the `Close` action to `C-A-c`.

This tiling configuration is based on:

https://thomashunter.name/posts/2019-01-27-treating-openbox-like-a-tiling-windowmanager
.

Under `Keybindings for running applications` paste the following:

```xml
    <keybind key="C-A-Up">
      <action name="ToggleMaximize"/>
    </keybind>

    <keybind key="C-A-Down">
      <action name="Iconify"/>
    </keybind>

    <keybind key="C-A-q">
      <action name="Close"/>
    </keybind>
    <keybind key="C-A-Left">
      <action name="Unmaximize" />
      <action name="MoveResizeTo">
        <x>0</x>
        <y>0</y>
        <width>50%</width>
        <height>100%</height>
      </action>
    </keybind>

    <keybind key="C-A-Right">
      <action name="Unmaximize" />
      <action name="MoveResizeTo">
        <x>-0</x>
        <y>0</y>
        <width>50%</width>
        <height>100%</height>
      </action>
    </keybind>
```
.

This gives you the following keybinds:

| Action     | Keybind            |
|------------|--------------------|
| Maximize   | ctrl + alt + up    |
| Minimize   | ctrl + alt + down  |
| Tile Right | ctrl + alt + right |
| Tile Left  | ctrl + alt + left  |

.

In the `<applications>` section, which should be at the end of the file, add the following block:

```xml
  <application type="normal">
    <maximized>true</maximized>
    <decor>no</decor>
  </application>
```

This removes decorations from maximized windows.

### Ubuntu KDE proot-distro Desktop Setup

First, do steps 1,2,4,5,6,8 and 9 from the [LXQT Installation](#lxqt-installation) section.

#### Ubuntu KDE Installation

1. Run these commands in Termux:

```bash
pkg in -y proot-distro
proot-distro install ubuntu
proot-distro clear-cache
proot-distro login ubuntu
apt -y update
apt -y upgrade
apt -y install kde-plasma-desktop ssh sudo tigervnc-standalone-server locales curl terminator fonts-ibm-plex bash-completion
apt -y remove plasma-discover
apt -y autoremove
locale-gen en_US.UTF-8 # Or your locale.
useradd <YOUR-USER-NAME>
chsh -s /bin/bash <YOUR-USER-NAME>
passwd <YOUR-USER-NAME> # Set your password.
echo '<YOUR-USER-NAME> ALL = (ALL) NOPASSWD: ALL' >/etc/sudoers.d/<YOUR-USER-NAME>
exit
```
.

Don't forget to substitute your actual username.

2. Put the following into your `~/.bash_profile`:

```bash
if [ -z "$TERMUX_VERSION" ]; then
    source ~/.bashrc
fi
```
.

3. Run the following in Termux:

```bash
proot-distro login ubuntu --user <YOUR-USER-NAME> --termux-home
vncpasswd # Set password to "termux".
exit
```
.

4. Edit your `~/.bashrc` to set a different `PATH` depending on whether you are in Termux or in Ubuntu and make some other necessary tweaks, it should look something like this:

```bash
if [ -n "$TERMUX_VERSION" ]; then
    export PATH=~/.local/bin:/data/data/com.termux/files/usr/bin
else
    export PATH=~/.local/bin:/usr/bin:/usr/local/bin:/sbin:/usr/sbin:/usr/local/sbin
fi

if [ -n "$TERMUX_VERSION" ]; then
    export XDG_RUNTIME_DIR=$TMPDIR
else
    mkdir -p /tmp/runtime-<YOUR-USER-NAME>
    chmod 700 /tmp/runtime-<YOUR-USER-NAME>
    export XDG_RUNTIME_DIR=/tmp/runtime-<YOUR-USER-NAME>
fi

if [ -n "$TERMUX_VERSION" ]; then
    pulseaudio --start
else
    export PULSE_SERVER=127.0.0.1
fi

alias ubuntu='proot-distro login ubuntu --user <YOUR-USER-NAME> --termux-home --fix-low-ports --shared-tmp'

if [ -z "$TERMUX_VERSION" ]; then
    alias ps='ps -e'
fi
```
.

This also gives you the `ubuntu` alias which you can use to login to your Ubuntu environment from Termux and a Termux native desktop, from there you can also launch graphical programs.

Don't forget to substitute your actual username.

5. Edit the file `/data/data/com.termux/files/usr/etc/pulse/default.pa` and change the line that looks like this:

```
#load-module module-native-protocol-tcp
```

to remove the leading `#` character, so it looks like this:

```
load-module module-native-protocol-tcp
```
.

6. Run these commands in Termux:


```bash
mkdir -p ~/.shortcuts/tasks
cd ~/.shortcuts/tasks
touch ubuntu-kde
chmod +x ubuntu-kde
```
.

7. Put the following into the file `~/.shortcuts/tasks/ubuntu-kde`:

```bash
#!/data/data/com.termux/files/usr/bin/sh

pulseaudio --start
rm -rf /data/data/com.termux/files/usr/tmp/.X1*
(
    sleep 4
    am start -a android.intent.action.VIEW -d vnc://localhost:5901/C24bit/termux >/dev/null
) &
proot-distro login ubuntu --user <YOUR-USER-NAME> --termux-home --fix-low-ports --shared-tmp -- vncserver -fg
```
.

Don't forget to substitute your actual username.

8. Put Termux:Widget into the widget area of your launcher and launch the ubuntu-kde task to open the desktop.

#### KDE Configuration

1. Launch the ubuntu-kde task to open the KDE desktop.

2. Go to `Settings -> Display and Monitor` and set global scale to 175% or your chosen scale. Logout and relaunch the task for it to take effect. You may need to experiment a bit to find the right scale for your tablet.

3. Go to `Settings -> Workspace Behavior -> Screen Locking` and turn off screen lock as well as lock after sleep. Disable the keyboard shortcut.

4. Go to `Settings -> Appearance -> Global Theme` and choose Breeze Dark.

5. Right click on the panel, click more options, choose auto hide. Press the red close button on the bottom and top panels.

6. Go to `Settings -> Shortcuts -> Shortcuts -> Kwin` and set the following keybindings:

| Action                  | Settings                                        |
|-------------------------|-------------------------------------------------|
| Quick tile window right | disable meta + right, set to ctrl + alt + right |
| Quick tile window left  | disable meta + left,  set to ctrl + alt + left  |
| Maximize window         | disable meta + down,  set to ctrl + alt + up    |
| Show desktop            | disable meta + d,     set to ctrl + alt + d     |
| Close window            | disable alt + f4,     set to ctrl + alt + c     |

and click apply.

7. Go to `Settings -> Window Management -> Window Behavior` and set window activation policy to focus follows mouse. Click apply.

8. Follow the steps in the [Kiwi Browser Launcher Configuration](#kiwi-browser-launcher-configuration) section and then go to `Settings -> Applications -> Default Applications` and select Kiwi Browser for web browser.

#### Terminator Terminal Configuration

1. Open the Terminator terminal and right click within the window, go to `Preferences`. 

Under `Global` set:

| Setting                            | Value        |
|------------------------------------|--------------|
| Unfocused terminal font brightness | 100%         |
| Mouse focus                        | follow mouse |
| Tabs homogeneous                   | deselect     |
| Hide size from title               | select       |

.

Under `Profiles -> Default -> General` set:

| Setting                     | Value                          |
|-----------------------------|--------------------------------|
| Use system fixed width font | deselect                       |
| Font                        | IBM Plex Mono Regular, size 11 |
| Show titlebar               | deselect                       |
| Cursor blink                | deselect                       |

.

Other fonts you can try, to see which one you like better, are Hack and DejaVu Sans Mono. The Ubuntu package for Hack is `fonts-hack-ttf`, and the packages for DejaVu fonts are `fonts-dejavu-core` and `fonts-dejavu-extra`.

Under `Profiles -> Default -> Colors -> Palette -> Built-in Schemes` select Tango.

Under `Profiles -> Default -> Background` select transparent background and set shade background to `0.70`.

Under `Profiles -> Default -> Scrolling` set scrollbar is disabled, and set scrollback to `30000`.

Under `Keybindings` set the following:

| Action            | Keybind                        |
|-------------------|--------------------------------|
| Copy              | shift + ctrl + alt + c         |
| Paste clipboard   | shift + ctrl + alt + p         |
| Paste selection   | shift + ctrl + alt + v         |
| New tab           | shift + ctrl + alt + t         |
| Resize right      | press backspace to disable     |
| Resize left       | press backspace to disable     |
| Next tab          | shift + ctrl + right           |
| Previous tab      | shift + ctrl + left            |
| Close term        | shift + ctrl + alt + q         |

, paste selection may not be available yet in the current Terminator package.

2. In KDE go to `Settings -> Window Management -> Window Rules`, click Add New, and set the following:

| Setting                     | Value                     |
|-----------------------------|---------------------------|
| Description                 | Undecorate Terminator     |
| Window class                | "Terminator", Exact Match |
| Match whole window class    | No                        |

. Click Add Property and under Appearance select No titlebar and frame. Select Apply Initially - Yes.

Click apply, restart Terminator.

#### Optional KDE Configuration

1. To change your time format and measurement units to the standard, go to `Settings -> Regional Settings -> Formats` and enable detailed settings. Choose the Germany locale with your language for time and measurement units, for English this would be `Germany English (en_DE)`. Then run the following commands in the terminal:

```bash
sudo locale-gen de_DE.UTF-8
sudo localedef -i de_DE -f UTF-8 en_DE.UTF-8
```

adjusting for your language, then logout of KDE and relaunch the task.

#### Chromium Browser Installation

1. Go to https://github.com/ELWAER-M/install-chromium-without-snap and follow the instructions to run the script and install Chromium.

2. Run the following:

```bash
mkdir -p ~/.local/share/icons/hicolor/256x256/apps
cd ~/.local/share/icons/hicolor/256x256/apps
cp /usr/share/icons/hicolor/256x256/apps/chromium.png .
cd
touch ~/.local/bin/chromium
chmod +x ~/.local/bin/chromium
```
.

3. Put this script into the `~/.local/bin/chromium` file:

```bash
#!/data/data/com.termux/files/usr/bin/sh

set -- /usr/bin/chromium --no-sandbox --enable-features=WebUIDarkMode --force-dark-mode "$@"

if [ -n "$TERMUX_VERSION" ]; then
    proot-distro login ubuntu --user <YOUR-USER-NAME> --termux-home --fix-low-ports --shared-tmp -- "$@"
else
    "$@"
fi
```
and substitute your actual username.

4. Edit the file `~/.local/share/applications/chromium.desktop` and change the `Exec` and `Icon` fields as follows:

```ini
Exec=/data/data/com.termux/files/home/.local/bin/chromium %U
Icon=/data/data/com.termux/files/home/.local/share/icons/hicolor/256x256/apps/chromium.png
```
.

5. Open Chromium and click the three dots on the top right, go to Settings, click advanced and under `Downloads -> Location` click change. Click other locations and navigate to `computer -> data -> data -> com.termux -> files -> home -> storage -> downloads`, click open.

6. In Chromium Settings under Startup set continue where you left off.

You can use this Chromium setup in both a Termux native desktop and in Ubuntu.

### Kiwi Browser Launcher Configuration

1. Run the following commands in Termux:

```bash
mkdir -p ~/.local/share/applications ~/.local/share/icons/hicolor/72x72/apps ~/.local/bin
cd ~/.local/share/icons/hicolor/72x72/apps
curl -L 'https://github.com/kiwibrowser/src.next/raw/kiwi/chrome/android/java/res_chromium_base/mipmap-hdpi/app_icon.png' -o kiwi.png
touch ~/.local/bin/kiwi
chmod +x ~/.local/bin/kiwi
```

2. Put the following script into the `~/.local/bin/kiwi` file:

```bash
#!/data/data/com.termux/files/usr/bin/sh

/data/data/com.termux/files/usr/bin/am start -n com.kiwibrowser.browser.dev/com.google.android.apps.chrome.Main -a android.intent.action.VIEW ${@:+-d} "$@" >/dev/null 2>&1
```

3. Put the following into the `~/.local/share/applications/kiwi.desktop` file:

```ini
[Desktop Entry]
Encoding=UTF-8
Version=1.0
Type=Application
Terminal=false
X-KDE-Protocols=https,http,ftp
Exec=/data/data/com.termux/files/home/.local/bin/kiwi %u
Name=Kiwi Browser
Icon=/data/data/com.termux/files/home/.local/share/icons/hicolor/72x72/apps/kiwi.png
MimeType=text/html;text/xml;application/xhtml+xml;text/mml;x-scheme-handler/http;x-scheme-handler/https;application/x-www-browser;
StartupNotify=true
Categories=KDE;Network;WebBrowser;
Keywords=web;browser;internet;
```

4. Run `update-desktop-database`.

5. Set the default web browser to Kiwi Browser in your desktop environment.
