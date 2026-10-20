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
Potential use by an animal was identifyed by searching for delta temperature changes in the downloaded data  
The methodology is explained in detail within the paper.
# Proposal
Pre-process the temperature change date to derive and store an 'event' within the logger.  
This vastly reduces the amount of data stored with consequential cost and power consumption savings.  
(Does require custom hardware and software).  
It would be possible to store detailed samples pre and post trigger (the Joyce method does identify false events).  
Most efficently, not as raw data, but a string of values e.g. "< &#916;t 5&deg;C/min >"  
(It is proposed that the trigger &#916;temperature and &#916;time would be user configurable).  
   
 - 
# Parameters:
- Occupancy: binary state time-stamped
- Maximum and minimum temperatures 


# Features:
Hardware Changes:
 *  Microchip 12F683 to time reset from sleep and reset on external input
 *  Logging: saving homeopathic amounts of data, 4 bytes hourly - 8 bytes daily  
 *  Maybe EEPROM? space for 512 days of daily data. Write endurance 10,000 days
 *  RTC memory enough for last two days worth of hourly data..maybe pop some into EEPROM
Software Changes:
 *    WiFi-GUI as AP - no LAN so direct GUI connection to mobile device - implemented 20/12/23
 *    Powersave: ESP runs once to log load and solar power: reset every 40 seconds by 12F683
 *    Epever RTC used hourly to save watt/hour figures to FRAM
 *    If load state toggled - ESP+wifi+GUI powered for 10 mins (use Epever RTC to time this?)
 *    Managed by GUI banner with timeout - reset by GUI pushbutton?
 *    Midday Load OFF - every day - 

![grafik](https://github.com/hedley-a/EPEverDatalogger/assets/30367667/bc1038a8-85d1-49f0-b62f-6d7b42dab50c.png)

![grafik](https://github.com/hedley-a/EPEverDatalogger/assets/30367667/a847ab49-01aa-47ac-b780-41ef428c1dc6.png)


#
- [![LICENSE](https://licensebuttons.net/l/by-nc-nd/4.0/88x31.png)](https://creativecommons.org/licenses/by-nc-nd/4.0/)
