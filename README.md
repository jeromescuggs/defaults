## a collection of configs!

![](https://github.com/jeromescuggs/defaults/blob/master/ss-1.png?raw=true)

### misc programs
- feh (`sudo apt install feh`)
  - after setting a background image with feh, add `exec_always --no-startup-id sh $HOME/.fehbg` to i3 config
- blurwal (`sudo pip3 install blurwal`) 
  - compliments `feh` and when running, applies a smoothly-transitioning blur effect to your background, when a user-defined number of windows are open. 
- bpytop (https://github.com/aristocratos/bpytop)
  - requires `python3-psutil` package from apt
  - clone git repo, navigate to folder, run `make install`. 
- polybar 
  - easiest way to install is via the speed-ricer PPA maintained by kgilmer, for the awesome Regolith distro - a tweaked ubuntu image with a host of nifty defaults such as i3wm and conky etc. 
  - add the PPA: `sudo add-apt-repository -y ppa:kgilmer/speed-ricer`
  - run `sudo apt update`
  - and finally, `sudo apt install polybar`

