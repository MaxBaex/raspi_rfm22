raspi_rfm22
===========

RFM22 MAC driver for Raspberry PI using wiringpi and RPIO. 
The driver supports sending and receiving of packets. 
To prevent collisions the driver waits for the medium to become
free (Free channel assessment) befor sending. 


Next steps, limitations:
------------------------
CSMA/CA with a random delay is missing. 
Reading RSSI does not work yet. 


Install:
--------
Get the RPIO library for the Raspberry PI:  http://pythonhosted.org/RPIO/
Get the wiringPi Module for Python: https://github.com/WiringPi/WiringPi2-Python

Connect the RFM22 Module to the GPIO Header. See code for detailed wiring 
description. 

