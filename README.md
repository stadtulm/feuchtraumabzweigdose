# Feuchtraumabzweigdose

This PCB is meant to function as an experimental playground for the [OpenBike](https://ulm.dev/projects/openbike/) project. It integrates WiFi and Bluetooth via the ESP32 MCU and LoRaWAN through the ubiquitous RFM95W modem. It also has a dedicated header for a gyro module as well as a switchable power supply for GNSS/GPS modules that can be switched off for deep sleep. It exposes a shared SPI bus, two serial lines and all unused pins of the ESP32, with several RTC interrupt methods available in hardware. A dedicated dynamo-to-Li+ charger as well as an efficient 3.3V LDO to supply the logic can be populated optionally. 

All in all it is an attempt to migrate most of the functionality of a TTGO T-Beam while being able to run days or weeks on end on one 18650 cell while mostly being in deep sleep. The T-Beam will usually deplete the cell within 30 hours.

For full functional documentation see [`docs/feuchtraumabzweigdose.pdf`](docs/feuchtraumabzweigdose-docs.pdf).

The project is named Feuchtraumabzweigdose because it is meant to fit snugly into a waterproof junction box – or Feuchtraumabzweigdose in German :D

## Known issues

* stk forgot the pullup resistors on the BOOT and RESET buttons respectively. This can be mitigated through botch wire.
* stk probably also forgot a pulldown resistor for the interrupt on the MPU9250 breakout header. Botch wire, again.
* as of now, the circuit has no undervoltage protection for the 18650. Use protected cells, if possible
