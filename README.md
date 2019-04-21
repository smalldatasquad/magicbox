# magicbox


## Pi setup


#### Enable SSH

`sudo raspi-config`

select: `Interfacing Options > SSH`, turn SSH on.
Optionally, install mosh: `sudo apt-get install mosh`

#### Change password
`passwd`

#### Set hostname
```
sudo echo "magicbox" > /etc/hostname
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install avahi-daemon
```
Edit `/etc/hosts` so there is a line:
`127.0.0.1       localhost localhost.localdomain magicbox`

#### Set DNS servers
```
sudo echo "interface eth0
static domain_name_servers=8.8.8.8" >> /etc/dhcpcd.conf
```

#### Install/update Node via nvm
```
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.9/install.sh | bash
```
log out, then log in:
```
nvm install node
nvm use node
```

#### Install Vim

`sudo apt-get install vim`

## Process management with pm2

- Install pm2: `npm install pm2@latest -g`
- Setup pm2 startup script: Run `pm2 startup`, then run the resulting command
- Run scripts with pm2 (for example, messybot): `pm2 start EXAMPLEAPP.js`
- Save scripts for startup: `pm2 save`
