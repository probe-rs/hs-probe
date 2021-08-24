# The Rusty High-speed Probe

This is an open hardware probe for the Serial Wire Debug (SWD) and JTAG protocol. It utilizes an
STM32F723 MCU which has an USB 2.0 High-speed Phy.

## Firmware

The firmware is available here and is open-source: https://github.com/probe-rs/hs-probe-firmware

## Features

There is an USB MUX on the board, so when the probe starts it enumerates in USB FS where one can
access the internal bootloader, and then when the firmware takes over it can switch to the USB HS.

* The output connector can either be:
    * The STDC14 connector used on STLink/V3 which is mounted by default.
    * Or the standard Cortex-M Debug (1.27mm, 10 pin) connector if one bends/removes the outer 2 pins on the connector.
* The programming connector is the Tag Connect TC2030, however for just loading firmware the USB bootloader is recommended.
* USB MUX between USB HS/FS.
* Castellated vias for all programming pins, power and 2 GPIOs.
* USB-C connector.
* Target 5V and 3.3V is protected with an ideal diode circuit to not have current flow from the target to the host.
* For compatibility (mainly with Tag-Connect TC2050), pin 7 on the STDC 14 can be connected to the protected 5V.

The schematic can be found in [the schematic PDF](schematic-v1.3.pdf).

![alt text](hs-probe-top.jpg "probe")
![alt text](hs-probe-bot.jpg "probe")

## Cable Assembly

The hs-probe package sold on our [shop](https://shop.probe.rs) contains two 16 wire ribbon cables, three 14p connectors and one 10p connector.
You can make one cable with a 14p connector on each side and one cable with a 14p connector on one and a 10p connector on the other side. How to align the connectors is explained in the image below:

![alt text](docs/cable-asssembly-instructions.png "cable assembly")

## License

This work is licensed under [CERN-OHL-P](cern_ohl_p_v2.txt).
