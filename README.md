
arduino-cli core update-index
arduino-cli core install arduino:avr
arduino-cli compile --fqbn arduino:avr:uno .
arduino-cli upload -p /dev/ttyACM0 --fqbn arduino:avr:uno .

arduino-cli lib search debouncer
arduino-cli lib install FTDebouncer


## Update USBasp firmware

https://blog.lincomatic.com/converting-cheap-chinese-usbhid-fake-usbasps-into-real-usbasps/
https://forum.arduino.cc/t/autoreset-disabling/350095
https://per1234.github.io/ino-troubleshooting/burn-bootloader.html#:~:text=Invalid%20device%20signature.,determine%20your%20board's%20SPI%20pins.
https://www.electronics-lab.com/project/usbasp-firmware-update-guide/
https://ww1.microchip.com/downloads/en/DeviceDoc/ATmega8A-Data-Sheet-DS40001974B.pdf
https://www.fischl.de/usbasp/
https://irq5.io/2017/07/25/making-usbasp-chinese-clones-usable/

```bash
./avrdude -v -P /dev/ttyACM0 -C ../etc/avrdude.conf -c avrisp -b 19200 -pm8 -U flash:w:usbasp.atmega8.2011-05-28.hex:i
```
