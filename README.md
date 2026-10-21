# Marten box occupancy logger
![grafik](https://github.com/hedley-a/Marten-Logger-BLE/blob/main/images/DenBox_front.jpg)
## Marten box inside view
![grafik](https://github.com/hedley-a/Marten-Logger-BLE/blob/main/images/DenBox_interior.jpg)

- Objectives: A low cost, reliable and easy to use logging device
- Improving upon the method of detecting occupancy used in the Joyce North American study
## [Joyce Study](https://stacksjournal.org/wp-content/uploads/2025/06/Joyce-25003-Article.pdf)
   _"Each den box had an internal temperature logger (HOBO® UA-001-64
     pendant logger or MX2201, Onset Computer Corporation, Massachusetts,
     USA) that was screwed to an inside wall roughly 5 cm above the top of the
     wood chip bedding material, close to the bottom of boxes so that animals resting
     in den boxes would be more likely to heat the air around
     temperature loggers. "_  
     
Temperatures were sampled every 5 minutes over 4 months.  
Potential use by an animal was identifyed by searching for temperature changes in **den data only**  
The methodology is explained in detail within the paper.  

## Differential meausurment
The Joyce study did not use differential meausurement due to the cost of deploying two loggers.  
Comparing the temperature in the nest-box with the entrance area with our hardware is simple, cheap and improves data integrity.  

# Planned Improvements
- Differential meausurments reject common mode change: e.g sunlight on box, diurnal and seasonal.  
- Store only 'changing data'.    
- Vastly reduces the amount of data with consequential cost and power consumption savings within the logger.
- Less data to recover, analyse and discard post download   
- Does require custom hardware / software.  

## Hardware
- Nordic Semiconductor NRF52832 Bluetooth Module BLE 4.2 Low Power Bluetooth module
- 1024k of EEPROM memory (2 x  
- Passive NTC thermistor differential bridge temperature sensors  
- SHT41 Temperature and *Humidity!* sensor(external enviroment)
- ABS box
- Stainless Steel immersion sleeves
- 2 AAA Lithium Iorn disulphide cells and holder
- Hand wired
- Approx £25-30 as prototype, cheaper in quantity.
  
### Data Storage:
1024k of EEPROM memory 131,072 Bytes
#### Triggered logging
- Assume four daily occupancy events where differential probe temperature triggers detailed recording.
- Each event record could be up to one hour at 2 minute sampling: 30 readings of +/- 12°C diff @ 0.1°C resolution.
- **120 bytes/day**
- Regular enviromental monitoring - every four hours:  Internal, External Max/ Min @ 1°C resolution
- **24 bytes/day**
- append a 4-byte epoch timestamp to every regular log and random event,
- daily consumption **184 bytes**
- Capacity:  **712 days** before oldest data overwritten

#### Continuous logging
- Increase logging interval to five minutes
- Reduce data to one byte - just the +/- 12°C diff @ 0.1°C resolution.
- **288 bytes/Day**
- Regular enviromental monitoring - every four hours:  Internal, External Max/ Min @ 1°C resolution
- **24 bytes/day**
- No need for timestamps due to regularity.
- **312 bytes/day**
- **131,072/312 = 354 days**
### Recommendations
 The differential approach is key to storing data efficently.
- Continuous logging, as opposed to event triggered still provides sufficent duration and simplifies software devlopment.
- There is a risk with triggering that events are missed or spurious data recorded.
- it is expected that using temperature analysis to determine box occupancy may become unreliable during periods of high ambient temperature.   
### Risks
- nRF52 development kit for debugging / programming  - working, tested
- There is a plenty of boiler-plate code and 
- 'Hello world' BLE (bluetooth low energy) connection with Nordic smartphone APP - tested
- IANAE but with a bit of help (not all, hopefully from AI) this project should be do-able 
 
# Deployment:
Two 6 mm holes drilled into the base of the box on either side of one internal nest-box baffle
Probe/logger assembly robust, simple to deploy and service.  
Data - one year of storage - download by Bluetooth 
![grafik](https://github.com/hedley-a/Marten-Logger-BLE/blob/main/images/DenboxProbes.png)  

## [Box modification drawing](https://github.com/hedley-a/Marten-Logger-BLE/blob/main/monitor_box.pdf)

## [Circuit diagram](https://github.com/hedley-a/Marten-Logger-BLE/blob/main/schematic_dbl.pdf)




