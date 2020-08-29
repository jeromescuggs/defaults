## a collection of configs!

![](https://github.com/jeromescuggs/defaults/blob/master/ss-1.png?raw=true)

## BEWARE!

these configs are still pretty messy and far from optimized - in particular the i3 config, which comes from my WSL setup and therefore has some counter-intuitive keys setup. while simply copying all the files won't (probably) break your desktop beyond repair, i would advise giving them a bit of scrutiny before using them, and tweak to your own needs. 

### misc programs
- feh
  - after setting a background image with feh, add `exec_always --no-startup-id sh $HOME/.fehbg` to i3 config
- blurwal (`sudo pip3 install blurwal`) 
  - compliments `feh` and when running, applies a smoothly-transitioning blur effect to your background, when a user-defined number of windows are open. 
- bpytop (https://github.com/aristocratos/bpytop)
  - requires `python3-psutil` package from apt
  - clone git repo, navigate to folder, run `make install`. 
- rofi (`sudo apt install rofi`)
  - for dmenu-esque launcher, add `bindsym $mod+Shift+space exec rofi -show drun` to i3 config
  - for the window switcher, add `bindsym $alt+Ctrl+space exec rofi -show window` to i3 config
