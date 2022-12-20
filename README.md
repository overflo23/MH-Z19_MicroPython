# MH-Z19 CO2 Sensor from Winsen

__MH-Z19B + MH-Z19C driver for MicroPython__



This library implements a simple class to get data from the MH-Z19 Sensors

It will tell you 
* PPM 
* Room temperature (not very accurate) - not documented in Module Datasheet
* CO2 Status (whatever that is)  -   Neither documented in Module Datasheet



Author: Florian "overflo" Bittner - 12/2020 

 [Projects](https://overflo.info) 
 
 [Twitter](https://twitter.com/overflo) 
 
 [Github](https://github.com/overflo23)



*Version 0.1*

__License MIT__


Some hints taken from:
https://github.com/nara256/mhz19_uart/blob/master/src/MHZ19_uart.cpp
https://emariete.com/en/sensor-co2-mh-z19b/#El_sensor_de_CO2_MH-Z19C




USE LIKE:

```
import mhz19

#init sensor on UART #1
sensor = mhz19.mhz19(1)

#update data from sensor
sensor.get_data()

print('ppm:',    sensor.ppm)
print('temp:',   sensor.temp)
print('status:', sensor.co2status)
```

CALIBRATE IF NEEDED:
```
#perform a manual zero point calibration (let it sit at 400pm for 20mins first)
sensor.calibrate_zero()

#enable/disable automatic zero point calibration, which depends on a daily drop
#to 400ppm to work
sensor.set_auto_calibrate_zero(True)
```
