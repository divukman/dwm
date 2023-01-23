# DWM Configuration  
  
 DWM  https://suckless.org/
  
## Patches  
  
| patch | url  |
|--|--|
| systray | https://dwm.suckless.org/patches/systray/ |

 
 ## dwm `config.h` 

- @todo:  
  
 ## xsession desktop `dwm.desktop`
 
 `/usr/share/xsession/dwm.desktop`
 
 ```
 [Desktop Entry]  
Encoding=UTF-8  
Name=Dwm  
Comment=Dynamic window manager  
#Exec=/usr/local/bin/dwm
Exec=/usr/local/bin/dwm-custom-init
Icon=dwm  
Type=XSession
 ```

## dwm custom init script
  
  `/usr/local/bin/dwm-custom-init`
  ```
  #!/bin/sh
  xset -dpms # disable screen power saving settings
  xset s off # disable screen blanking
  xsetroot -solid black # set background color to black
  setxkbmap -option grp:switch us,hr # set up keyboard layout as US english (or hr when Alt Gr is pressed)
  volumeicon & # show volume icon in system tray
  nm-applet & # show network applet in system tray
  dwm # run dwm
 ```

## Apps  

| app | arch install | run
|--|--|--|
| network manager applet | $ sudo pacman -S network-manager-applet   | nm-applet
| alsa utils | $ sudo pacman -S alsa-utils    | alsamixer
| volumeicon | $ sudo pacman -S volumeicon    | volumeicon


