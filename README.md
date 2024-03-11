# rtc-tasmota

https://components101.com/modules/ds3231-rtc-module-pinout-circuit-datasheet
Power supply for RTC module -  2.3V – 5.5V
The following commands need to be used
-Time (Time command will disable NTP sync)
- NTP server can be activated with the command RtcNtpServer 1 and deactivated with RtcNtpServer 0 ( I don't think I will need to configure this)
## Vin for Node MCU
- Vin should be between 4.75V and 10V (https://arduino.stackexchange.com/questions/76118/nodemcu-power-supply)
## For custom edit
- I use Docker with my Raspberry Pi 4. ( See in the other thread)
