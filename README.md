# MUT 3S BOX


# Inspiration
91-95 3000GT / Stealth cars have no support from commercial and easy to get readers since they use a simpler protocol with specific init.

In the old days there were a few projects that supported the platform like:
- Palm based MMCDLogger (91-93):  https://mmcdlogger.sourceforge.net/
- Mitsulogger (94-95+): https://github.com/dparrish/ecurom/tree/master/tools/MitsuLogger

And the commercial cables/loggers like:
HHH, EvoScan, pocket logger.


The free DIY involved:
- 1G: Get the MMCDLogger and a palm emulator, build a DSM logger cable (got the diagram from https://www.dsmtuners.com/threads/how-to-set-up-mmcd-make-a-logging-cable.203316/) and get an RS232 adapter.

![Image of a 1g logging diagram](https://www.dsmtuners.com/attachments/palmminimalist4cj-jpg.291632/)
- 2G: Get the Mitsulogger, build a K-Line circuit DIY cable with an FTDI adapter (The first time I saw and built one with: https://www.3si.org/threads/anyone-up-for-a-7-hybrid-logging-cable.436691).

![Image of a 2g logging diagram](images/obdii_avr.gif)


Then I found this:
https://github.com/muki01/OBD2_K-line_Reader/

The K-line reader was familiar and I had used a similar approach with an arduino for the 1G, since the protocol is simple and I know the requests from evoscan/mitsulogger/mmcdlogger.

But the whole standalone webserver UI from the ESP32 was a great and cool idea so I followed and built that, works great and has a more universal approach to logging.



## Supported vehicles
Mitsubishi MUT / Hybrid years
91-93 simple request-response message.
94-95 k-line 5 baud init.

96+ are OBD2 compliant and can use any commercial dongle/cable/reader.


## Required hardware
- ESP32 (Here I used a ESP32 Wroom 32 DevKit / Doit ESP32 Devkit v1)
- PCB With voltage regulator and K-Line circuit (3 options, see: https://github.com/muki01/OBD2_K-line_Reader), I used the comparator approach.


⚠️ Critical Warning for ESP32-WROOM-32D / 32U
If your module is the ESP32-WROOM-32D or ESP32-WROOM-32U (the most common versions), GPIO 16 and 17 are completely unusable.

Safe general-purpose pins:
• GPIO 18, 19, 21, 22, 23, 25, 26, 27, 32, 33

## Required libraries
- ESPAsyncWebServer: https://github.com/ESP32Async/ESPAsyncWebServer (at least version 3.6.2)
- AsyncTCP: https://github.com/ESP32Async/AsyncTCP (at least version 3.3.2)
- ArduinoJson


