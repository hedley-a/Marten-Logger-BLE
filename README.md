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
Potential use by an animal was identifyed by searching for temperature changes in the data  
The methodology is explained in detail within the paper.
# Proposed Improvement
Differential meausurment rejecting common mode change: e.g sunlight on box, diurnal and seasonal.  
(Diagrams below).  
Store only 'changing data'.    
Vastly reduces the amount of data with consequential cost and power consumption savings.  
Does require custom hardware / software.  

## Hardware
- Nordic Semiconductor NRF52832 Bluetooth Module BLE 4.2 Low Power Bluetooth module  
- Passive NTC thermistor differential bridge temperature sensors  
- SHT41 Temperature and *Humidity!* sensor(external enviroment)
- ABS box
- Two fluid   
  
### Storage:
1024k of EEPROM memory program and data
- Occupancy: state time-stamped data  
- Daily maximum and minimum internal and external temperatures  
### Lifespan Estimate (64 KB Flash Partition)
• Daily Footprint: 4 events × 24 bytes + 16 bytes (Daily Min/Max) = 112 bytes / day.  
• Total Lifespan: A dedicated 64 KB partition will last ~585 days (~1.6 years) of continuous logging before needing a page rotation or overwrite.
### differential meausurment
The Joyce study did not use differential meausurement due to the cost of including two loggers. 
Comparing the temperature in the nest-box with the entrance area simplifies our hardware and software!. 
# Deployment:
Two 6 mm holes drilled into the base of the box on either side of one internal nest-box baffle
Brass probes integrated into the logger enclosure and inserted as part of fixing it underneath the box.  

  probe         probe
  |             |  
  |             |  
  |             |
------------------
|  Enclosure      |  
------------------



