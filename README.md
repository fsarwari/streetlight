# SmartSwitch

## Compile Tasmota with the following enabled in my_user_config.h
```
 #define USE_DS3231
 #define USE_RTC_ADDR  0x68
```


## Console commands to configure time and date
```
TimeSTD 0, 1, 11, 1, 2, -300
TIMEDST 0, 2, 3, 1, 2, -240
TimeZone 99
```

## Console commands to configure Location
```
latitude 43.856098
longitude -79.337021
```

## Console commands to configure switchmode 
```
switchmod1 3
```

## Console commands: fail-safe, power on if reset after timer
```
poweronstate 0
Rule1
  ON Time#Initialized DO Backlog event checksunrise=%time%; event checksunset=%time% ENDON
  ON event#checksunset>%sunset% DO Power1 1 ENDON
  ON event#checksunrise<%sunrise% DO Power1 1 ENDON
```
Source: https://tasmota.github.io/docs/Rules/#make-sure-light-is-on-at-night


## GPIOs
* D3 Swtich 1 (GPIO0)
* D1 I2C SLC  (GPIO5)
* D2 I2C SDA  (GPIO4)
* D0 Relay 1  (GPI16)

![alt text](https://github.com/fsarwari/smartswitch/blob/master/circuit.jpg?raw=true)
![alt text](https://github.com/fsarwari/smartswitch/blob/master/board-1.png?raw=true)
![alt text](https://github.com/fsarwari/smartswitch/blob/master/board-2.png?raw=true)
![alt text](https://github.com/fsarwari/smartswitch/blob/master/board-3.png?raw=true)
![alt text](https://github.com/fsarwari/smartswitch/blob/master/Tasmota-config.png?raw=true)

