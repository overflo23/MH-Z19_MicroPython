== MH-Z19 CO2 Sensor from Winsen


MH-Z19B + MH-Z19C  driver for MicroPython

Author: Florian "overflo" Bittner - 12/2020
Find me here:    https://overflo.info / https://twitter.com/overflo / https://github.com/overflo23


Version 0.1
License MIT


Some hints taken from:
https://github.com/nara256/mhz19_uart/blob/master/src/MHZ19_uart.cpp



This implements a simple class to get data from the MH-Z19 Sesors
It will tell you 
 - PPM 
 - Room temperature (not very accurate) - not documented in Module Datasheet
 - CO2 Status (whatever that is)  -   Neither documented in Module Datasheet



USE LIKE:

import mhz19

# init sensor on UART #1
sensor = mhz19.mhz19(1)

# update data from sensor
sensor.get_data()


print('ppm:',    sensor.ppm)
print('temp:',   sensor.temp)
print('status:', sensor.co2status)

