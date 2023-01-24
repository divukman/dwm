# DWM Configuration  
 
[DWM](https://suckless.org/)
  
  
## Installation

### Dependencies

#### Arch
```
sudo pacman -S base-devel libx11 libxft libxinerama freetype2 fontconfig
```
`sudo pacman -S xorg-xfontsel`

#### Debian
```
sudo apt install build-essential libx11-dev libxft-dev libxinerama-dev libfreetype6-dev libfontconfig1-dev
```

### Compile and install
```
mkdir .suckless
cd .suckless

git clone https://git.suckless.org/dwm
git clone https://git.suckless.org/st
git clone https://git.suckless.org/dmenu

cd .suckless

cd dwm
make
sudo make clean install
cd..

cd st
```
Edit the config.h and change the font to:
`static char *font = "FreeMono:pixelsize=16:antialias=true:autohint=true";`

```
make
sudo make clean install
cd ..

cd dmenu
make
sudo make clean install

cd
```
  
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
  # xsetroot -solid black # set background color to black
  feh --bg-scale /usr/share/wallpapers/Maldives/maldives.jpg # custom wallpaper
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
| feh | $ sudo pacman -S feh    | feh

## Useful commands  

`fc-list - list fonts` 
`fc-match name - lsit best matching font` 

## Resources
- https://suckless.org/
- https://wiki.archlinux.org/title/dwm
- https://wiki.debian.org/Dwm
- https://wiki.gentoo.org/wiki/Dwm
- https://faun.pub/the-easiest-way-to-install-dwm-43bbf668ea83
- http://www.danamlund.dk/dwm_setup.html
- https://ratfactor.com/dwm
- 
