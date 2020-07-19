# The Rusty High-speed Probe

This is an open hardware probe for the Serial Wire Debug (SWD) and JTAG protocol. It utilizes an
STM32F723 MCU which has an USB 2.0 High-speed Phy.

There is an USB MUX on the board, so when the probe starts it enumerates in USB FS where one can
access the internal bootloader, and then when the firmware takes over it can switch to the USB HS.

* The output connector can either be:
    * The STDC14 connector used on STLink/V3 which is mounted by default.
    * Or the standard Cortex-M Debug (1.27mm, 10 pin) connector if one bends/removes the outer 2 pins on the connector.
* The programming connector is the Tag Connect TC2030, however for just loading firmware the USB bootloader is recommended.
* USB MUX between USB HS/FS.
* Castellated vias for all programming pins, power and 2 GPIOs.

The schematic can be found in [the schematic PDF](schematic-v1.1.pdf).

![alt text](hs-probe-top.jpg "probe")
![alt text](hs-probe-bot.jpg "probe")

## License

This work is licensed under [CERN-OHL-P](cern_ohl_p_v2.txt).
