## a collection of configs!

![](https://github.com/jeromescuggs/defaults/blob/master/ss-1.png?raw=true)

## BEWARE!

these configs are still pretty messy and far from optimized - in particular the i3 config, which comes from my WSL setup and therefore has some counter-intuitive keys setup. while simply copying all the files won't (probably) break your desktop beyond repair, i would advise giving them a bit of scrutiny before using them, and tweak to your own needs. 

### to build i3 with gaps+corners, and picom with corners: 

#### dependencies
~~~ bash
sudo apt install build-essential devscripts meson 
~~~

nifty trick to easily install all required `libxcb` packages
~~~ bash
sudo apt install $(apt-cache search ^libxcb | grep dev | cut -d' ' -f1)
~~~

#### i3
~~~ bash
cd gits
git clone https://github.com/resloved/i3
cd i3
git submodule update --init
autoreconf --force --install
mkdir build && cd build
../configure --prefix=/usr --sysconfdir=/etc --disable-sanitizers
make -j8
sudo make install
~~~

#### picom (aka compton)
~~~ bash
cd gits
git clone https://github.com/ibhagwan/picom
cd picom
meson --buildtype=release . build
ninja -C build
ninja -C build install
~~~


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
