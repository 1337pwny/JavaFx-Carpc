# JavaFx-Carpc
Carpc wirtten in JavaFx, 

![Car Image](/images/car_img_1.jpg)

## Language
Java (open-jdk 8, openjfx)

## Features
- Plays Musik via [Mpd](https://www.musicpd.org)
- Shows Navigation via [Navit](https://www.navit-project.org)
- Plays DAB+ Radio via [Welle.io](https://www.welle.io)
- Uploads GPS Tracks via http(s)
- Updates Musik via [owncloudcmd](https://doc.owncloud.org/desktop/1.8/owncloudcmd.1.html)

## Dependencies
- java-mpd
- json-simple

## Hardware
- Raspberrypi 3 or 4, (maby 2 never tested)
- Raspberrypi 7-Inch Touch Screen Display
- StromPi for 12V power Supply (or whaterver you whant to use)
- RTL2832 USB dongle (or whatever welle.io and your county supports)
- GPS USB dongle (or whatever gpsd supports)

## How to use
TODO

## Setup

### MPD
MPD is a musik Player that can be controllerd by a text interface over Network. So it is possible to controll the Musik played on your Car-Radio by Handy, PC, or whatever device you are using.
The recomended MPD version is 0.21.*. On previous versions download from Album covers wie text interface will not work and it will not be shown in the Player.

#### Setup on Raspian Buster
Just install mpd from you packet manager an you're fine

#### Setup on Raspian Stretch
First of all you don't want to do that !!!
Are you still here ?
Mhm ok...
Do you realy need the Album Covers? if not install last version from packet manager and be happy.
If not you have to compile mpd yourself and that means you need an actuall version of: gcc, cmake, boost, pyhton, meson, ninja.
For that have a look at the Scripts in the [setup_data/scripts/raspian_stretch] folder. That will keep your pi buissy for a howl day. For faster compiling you cann disable pyhton tests. Also you have to increase the virtual RAM of the rpy for compiling gcc. I changed it one GB and it worked fine.

### Feature Owncloud

### Feature Gps-Logging/Upload

### Feature Navit
For navigation is the Software [Navit](https://www.navit-project.org) used.
You cann install it via package manager or build it yourself.
On my rp3, I needet to to build it manually for Raspian Stretch for some reason (check scritps folder for that).
Navit loads all important Information from navit.xml. You can check out mine [here](/setup_data/navit/nativ.xml).
Most of it comes from [this Side](http://ozzmaker.com/navigating-navit-raspberry-pi)
Its also a very good tutorial how to get navit running.

## Configuration
There is a config file for dis/enableing Features and set up needet Folders and Files

### Comandline Paramters
- update -> just updates what is possible (gps,owncloud,mpd) witout showing gui
- debug -> sets log level to debug
- config=file -> changes used config file

### Config File Paramters
- ip (string) -> Default mpd IP (hostname or ip)
- ip_1 (string) -> Frist possible mpd ip for dropdown in settings
- ip_2 (string)-> Second possible mpd ip for dropdown in settings
- ip_* (string)-> You get it right ? Change number for next ip, max is 100
- width (int) -> width of window (not optimized for other resolution)
- height (int) -> height of window (not iptimized for other resolution)
- lighting_file (string) -> file on rpy where brightniss is saved
- lighting_min_value (int) -> minimal possible selectable brightness
- lighting_step_value (int) -> value of increasing brightness on one klick
- wlan_file (string)-> file on rpy where wlan status is stored
- wlan_interface (string) -> used wlan interface
- enable_owncloud (boolean)-> enables owncloud feature
- owncloud_host (string) -> url to owncloud bzw nextcloud server
- owncloud_dir (string) -> folder where data will sync
- enable_gps (string) -> enables gps upload feature
- gps_dir (string) -> folder where pgs data is loged
- gps_upload_url (string) -> url where gps data will be uploaded
- gps_upload_keystore (string) -> keystore with with private key
- gps_upload_keystore_pw (string) -> first password for keystore
- gps_upload_keystore_pw_2 (string) -> second password for keystore
- enable_radio (boolean) -> enables radio feature

### Images

![Image 0](/images/image_0.PNG)

![Image 0](/images/image_1.PNG)

![Image 0](/images/image_2.PNG)

![Image 0](/images/image_3.PNG)
