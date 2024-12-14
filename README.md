If you are looking to reflash a ShawLED Controller Board, this is the right place. <br>

Our Controller Boards use the Open Source WLED Firmware from AirCookie.  <br>
This firmware uses the MIT License and is heavily supported by the community  <br>
I will link at the bottom, more information on WLED - https://github.com/Aircoookie/WLED <br>

We recommend doing a complete flash by erasing the board entirely. <br>
Our older kits use a USB Micro connector while the newer ones will use a USB C <br>

You will need to get a CH340 driver on your laptop/PC in order for the OS to see the board. <br>
https://www.wemos.cc/en/latest/ch340_driver.html <br>

We use ESPTool to flash the firmware but there are a lot of options out there. <br>
https://github.com/espressif/esptool <br>

Install the CH340 driver, plug in your board and make sure you SO has it visible. <br>
Then follow the below steps if you are using esptool <br>

From a command prompt or powershell window, the following commands need to be run <br>

```
python -m esptool --port COM3 erase_flash
```

```
python -m esptool --port COM3 write_flash 0x1000 esp32_bootloader_v4.bin
```

```
python -m esptool --port COM3 write_flash 0x000000 SHAWLED_0.14.4_ESP32_Working_AP_
```
