# How to connect to a mikrotik via RJ45 Type Serial Port USB cable with FTDI chip on macos


This type of port is used on RouterBOARD 2011, 3011, 4011, CCR1072, CCR1036 r2 and CRS series devices, sometimes called "Cisco style" serial port.


If you locked out  your router serial console is your last option. 



atm drivers shipped with macos are not working. (25.02.2023)

your need to install the beta Virtual COM port (VCP) drivers drivers from  https://ftdichip.com/drivers/vcp-drivers/

Installer should be run from the Applications folder on your machine!

After installation you can find your serial usb cable in terminal: 
> type ls /dev/cu.*  

```
 mark@MacBook-Air-von-Markus ~ % ls /dev/cu.*                            
/dev/cu.Bluetooth-Incoming-Port	/dev/cu.wlan-debug  /dev/cu.usbserial-A9WKKTFL
```

you should see a device like  /dev/cu.usbserial-A9WKKTFL

then you can connect to your mikrotik console by typing
```

screen /dev/cu.usbserial-A9WKKTFL 115200

```

If you havent changed something 115200 is the correct speed.

As long u keep terminal window open u can plug as much console ports and jump from one router/ switch to another.

Happy troubleshooting!













Remarks:

https://developer.apple.com/documentation/systemextensions/installing_system_extensions_and_drivers

https://ftdichip.com/drivers/vcp-drivers/

https://wiki.mikrotik.com/wiki/Manual:System/Serial_Console

https://help.mikrotik.com/docs/display/ROS/Serial+Console


