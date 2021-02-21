## Raspberry Pi

### Set up

- Use
  [full Raspbian](https://www.raspberrypi.org/downloads/raspbian/); to
  get on SD card, use [Etcher](https://etcher.io/).

- `sudo raspi-config`:

  - change password
  - change host name
  - expand file system to use full SD card
  - boot to shell
  - configure time zone and locale (US english)
  - keyboard to Generic 101 PC / US (default is _UK_ and has `@` and
    `"` switched)
  - enable ssh (under "interfaces")


### Basic things

- Restart and stop: `sudo reboot` and `sudo halt`

- `apt-get update`

### Setting up wifi

- I think I can connect to the raspberry pi directly with an ethernet
  cable, if I need to re-set the wifi

- Looking in `/etc/network/interfaces`, it points to
  `/etc/wpa_supplicant/wpa_supplicant.conf` which has the key details

  ```
  network={
      ssid="[SSID]"
      psk="[password]"
      key_mgmt=WPA-PSK
  }
  ```
