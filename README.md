# rtc-tasmota

https://components101.com/modules/ds3231-rtc-module-pinout-circuit-datasheet
Power supply for RTC module -  2.3V – 5.5V
The following commands need to be used

- Time (Time command will disable NTP sync)
- NTP server can be activated with the command RtcNtpServer 1 and deactivated with RtcNtpServer 0 ( I don't think I will need to configure this)
## Vin for Node MCU
- Vin should be between 4.75V and 10V (https://arduino.stackexchange.com/questions/76118/nodemcu-power-supply)
## For custom edit
- I use Docker with my Raspberry Pi 4. ( See in the other thread)

## RTC connecting to Node MCU in Tasmota 
- https://tasmota.github.io/docs/DS3231/#tasmota-settings
  
![image](https://github.com/princekham/rtc-tasmota/assets/16104631/078b5ecd-e9b1-4dbc-9151-a008d08c89b9)

### For Custom compile, I added the following codes and RTC NTP server setup

```
#ifndef USE_RTC_CHIPS 
#define USE_RTC_CHIPS               // Enable RTC chip support and NTP server
#endif
#ifndef USE_DS3231
#define USE_DS3231                  // [I2cDriver26] Enable DS3231 RTC (I2C address 0x68) (+1k2 code)
#endif

#define RTC_NTP_SERVER


```
### For custom compile

- First open https://arendst-tasmota-1d5026udz4a.ws-us116.gitpod.io/
- then go to 'tasmota' on the left window
then click
 user_config_override.h 
paste your config file just above the last endif statement
- you can configure your SSID, etc in my_user_config.h
- then type in the command "platformio run -e tasmota"
- then under folder name 'build_output/firmware' , you will see tasmota.bin file
- from source (https://www.youtube.com/watch?v=WashxTcHiDc&ab_channel=vccground)
