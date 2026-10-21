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

### differential meausurment
The Joyce study did not use differential meausurement due to the cost of including two loggers. 
Comparing the temperature in the nest-box with the entrance area simplifies our hardware and software

# Planned Improvements
Differential meausurment rejects common mode change: e.g sunlight on box, diurnal and seasonal.  
Store only 'changing data'.    
Vastly reduces the amount of data with consequential cost and power consumption savings.  
Does require custom hardware / software.  

## Hardware
- Nordic Semiconductor NRF52832 Bluetooth Module BLE 4.2 Low Power Bluetooth module  
- Passive NTC thermistor differential bridge temperature sensors  
- SHT41 Temperature and *Humidity!* sensor(external enviroment)
- ABS box
- Stainless Steel immersion sleeves
- 2 AAA Lithium Iorn disulphide cells and holder
- Hand produced PCB
- Approx £25-30 as prototype, half that in quantity.
  
### Storage:
1024k of EEPROM memory
- Occupancy: time-stamped data  
- Hourly? maximum and minimum internal and external temperatures  

# Deployment:
Two 6 mm holes drilled into the base of the box on either side of one internal nest-box baffle
Probe/logger assembly robust, simple to deploy and service.  
Data - one year of storage  - download by Bluetooth 



  probe         probe
  |             |  
  |             |  
  |             |
------------------
|  Enclosure      |  
------------------



