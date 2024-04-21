## Getting Started

1. Use the [Raspberry Pi Imager tool](https://www.raspberrypi.com/software/) to flash an SD card with the latest image
    - Choose the ***Raspberry Pi OS Lite (32-bit) image*** for best speed
    - Click the gear icon to also setup WiFi and SSH or you may use a display and keyboard

2. SSH into the pi and update the kernel and reboot
- If the Pi imager was used, then you have the latest kernel, and may then only use apt-get update, skip reboot, and continue onto part 3
```

sudo apt-get update && sudo apt-get install raspberrypi-kernel
```
```
sudo shutdown -r now
```

3. Run the setup script
```
curl -s https://raw.githubusercontent.com/carboncomputers/piberry/main/pi/setup.sh | bash
```

## Details
- In ```/boot/cmdline.txt```, edit ```fbcon=font:VGA8x8``` to change the font/size if you wish. See [fbcon](https://www.kernel.org/doc/Documentation/fb/fbcon.txt) for more details
- Long holding the "End Call" key (~3 seconds) will trigger KEY_POWER and safely shutdown the pi
- Holding the "End Call" button during power up will put the keyboard into bootloader mode; it will now appear as a USB storage device and you can drag'n'drop the new firmware (\*.uf2) into the drive and it will reboot with the new firmware
