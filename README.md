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

Usage example:
-------------


    radio = Rfm22()
    radio.initialise()
    radio.start()
    u'''Wait some time to let the radio module time
    to initialise.'''
    time.sleep(1)
    
    u'''Send some data via RFM22. '''
    data = [10,20,30,40,50,60,70,80,90,100]
    for i in range(10):
        time.sleep(0.2)
        radio.put_tx_data(data, block=False)
        print "put to queue"
        
    u'''Receive data from RFM22'''
    #while(True):
        #data = radio.get_rx_data(block = True)
        #print "RX Data", data, "\n"
  
    u'''Join RFM22 thread.'''
    radio.join()
    

Donation:
---------
If find my code usefull. You can send me some money via Bitcoin:
Bitcoin adress:  1A9jgbDz5vZK4bgnUgEkSjL3VK4vb4bBka
