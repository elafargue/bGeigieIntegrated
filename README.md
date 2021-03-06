# bGeigieIntegrated
#### Integrated version of Safecast bGeigie device

We created an integrated version of the bGeigie device, a mobile survey Geiger counter. Our PCB is based on orginal design by [Safecast](https://github.com/Safecast/bGeigieNanoKit). We removed various breakout boards and instead placed most of the components directly on the PCB. Our design uses [RedBear Duo](https://github.com/redbear/Duo) as a central processing unit, instead of Arduino Fio. The entire circuit can be powered through USB connector on RedBear, or from a 3.7V LiPo battery. The circuit also includes a battery charger. For control of the Geiger gas tube the iRover is being used, just like in the original design. A LED and a piezo buzzer signalyze the incoming pulses. FGPMMOPA6H GPS receiver from Adafruit retrieves the current position of the device and an accelerometer/magnetometer (LSM303C form ST Microelectronics) measures acceleration and orientation of it. Data are being logged on a micro SD card. A socket for the XBee module is also included, which enables connection to an external logger. A monochrome, 128x32 pixels wide OLED graphical display from [Adafruit](https://www.adafruit.com/product/938) displays a simple user interface. Accelerometer/magnetometer uses an I2C interface. SD card and OLED display communicate via SPI. XBee and GPS module are using an UART interface.

-

#### Changes in schematic:

* Power supply:
 * automatic switch between battery or USB powered mode
 * software power-down
* GPS module:
 * connection to battery
 * uFL connector for external antenna
* OLED display:
 * changed to I2C interface
 * added socket for alternative [display](https://www.amazon.com/Diymall%C2%AE-Yellow-Serial-Arduino-Display/dp/B00O2LLT30)
* magnetic buzzer with integrated oscillator
* high brigthess LEDs for COUNT and LOG indication
* added rotary encoder
