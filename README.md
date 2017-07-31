# raspbian-jessie-lite_node-red_relays
First [download](https://www.raspberrypi.org/downloads/raspbian/) the Jessie Lite img and flash it to an sd card.
### Connect keyboard and screen to the Rpi
```sh
pi
raspberry
sudo nano /etc/wpa_supplicant/wpa_supplicant.conf
```

#### Add this:
```sh
network={
  ssid="NETWORK-NAME"
  psk="NETWORK-PASSWORD"
}
```
```sh
sudo raspi-config
```
- resize file system
- activate ssh
- memory split=16
```sh
sudo reboot
```

### move to Mac ssh..
```sh
ssh pi@raspberrypi.local
sudo apt-get update
sudo apt-get upgrade -y
sudo apt-get dist-upgrade
sudo apt-get clean
sudo reboot
```


## Install Node-RED, nodejs and npm
### Install NodeJS, NPM and Node-RED
```sh
bash <(curl -sL https://raw.githubusercontent.com/node-red/raspbian-deb-package/master/resources/update-nodejs-and-nodered)
```
- Type 'y' and then hit 'Enter' to start the install
```sh
sudo systemctl enable nodered.service
sudo systemctl start nodered.service
```
- You can now access Node-RED on ```raspberrypi.local:1880```
