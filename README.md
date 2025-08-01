# StardewValley-RPI5
HOW TO USE my Stardew Valley Setup on a Raspberry pi 5,
running raspian os bookworm or maybe even trixie.


0. Open terminal CTRL + ALT + T , & run ```sudo apt update && sudo apt upgrade - y``` and then once upgraded run ```wget -qO- https://raw.githubusercontent.com/Botspot/pi-apps/master/install | bash```
this  installs pi apps, then search steam, 
1. Visit first off my repository @ "https://github.com/SF-Rocker/0CrashSteamRunRPI5" # in your web browser not terminal yet.
2. Then do exactly what it says to disable the extra sound card feature Preclaim OSS device  that impacts performance, and prevents future crashes.
3. run ```dmesg``` to make sure you also followed the tutorial, how to remove the character error it throws.
4. run ```sudo ls -l /dev/cuse``` to show permissions steam has for its video driver support, otherwise it cannot run vulkan or opengl, i could be wrong.
5. run ```sudo chmod 777 /dev/cuse```
6. type ```sudo ls -l /dev/cuse``` again
 see the differences between ownership e.g. crw-------     <--- character device file for read and write. crwxrwxrwx  <--- chr,read, write and execute.
 crwxrwxrwx is the golden ticket to no crashes.
7.Open a Terminal and type ```cd Downloads``` ```git clone https://github.com/SF-Rocker/0CrashSteamRunRPI5.git```
if files get misplaced, figure out which directory you were supposed to be in first.
8. Follow the ReadMe document i posted on the https://github.com/SF-Rocker/0CrashSteamRunRPI5/tree/StartUp.services github
  It will show you how I made a boot script for running  ```sudo chmod 777 /dev/cuse``` on StartUp, don't  type it manually each time.
 It does it for you.
9. Open Steam from the pi apps store ```wget -qO- https://raw.githubusercontent.com/Botspot/pi-apps/master/install | bash``` search steam, and will reboot and  ask you to run 4 kb page size kernel?
    # See Step 0.
