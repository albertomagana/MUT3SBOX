# MUT 3S BOX


# Inspiration
91-95 3000GT / Stealth cars have no support from commercial and easy to get readers since they use a simpler protocol with specific init.

In the old days there were a few projects that supported the platform like:
- Palm based MMCDLogger (91-93):  https://mmcdlogger.sourceforge.net/
- Mitsulogger (94-95+): https://github.com/dparrish/ecurom/tree/master/tools/MitsuLogger

And the commercial cables/loggers like:
HHH, EvoScan, pocket logger.


The free DIY involved:
- 1G: Get the MMCDLogger and a palm emulator, build a DSM logger cable and get an RS232 adapter.
- 2G: Get the Mitsulogger, build a K-Line circuit DIY cable with an FTDI adapter.



## Supported vehicles
Mitsubishi MUT / Hybrid years
91-93 simple request-response message.
94-95 k-line 5 baud init.

96+ are OBD2 compliant and can use any commercial dongle/cable/reader.


## Required hardware
- ESP32
- PCB With voltage regulator and K-Line circuit (3 options, see: https://github.com/muki01/OBD2_K-line_Reader).



## Required libraries
- ESPAsyncWebServer: https://github.com/ESP32Async/ESPAsyncWebServer (at least version 3.6.2)
- AsyncTCP: https://github.com/ESP32Async/AsyncTCP (at least version 3.3.2)
- ArduinoJson


