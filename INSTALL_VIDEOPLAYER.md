# Video player install


## Install omxd

```
git clone https://github.com/subogero/omxd.git
cd omxd
make
make start
sudo make install
```

## Disable screen blanking

edit `/etc/xdg/lxsession/LXDE/autostart`

and add these lines:

```
@xset s noblank 
@xset s off
@xset -dpms
```
