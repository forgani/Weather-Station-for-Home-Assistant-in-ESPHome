## Weather-Station-for-Home-Assistant
The weather station measures speed and direction of wind, as well as temperature and humidity. The ESP32 is programmed with ESPHome to connect directly to Home Assistant.

## Sensors:
### Anemometer (Wind speed)

The Anemometer measures wind speed by closing a reed switch on each rotation. It’s plugged into the wind vane.  
Two pulses are given per full rotation of the wind cups.1 switch closure/second indicates 2.4 km/h (1.492 MPH).  
The Anemometer be pulled high to 3.3V via a 10 kΩ Pull-Up resistor. (Sales on AliExpress)  

### Wind Direction Sensor  (Wind vane)
The wind vane indicates the direction that the wind is blowing. This uses 4 magnetic reed switches, for North, East, South & West.  
Each direction has a different resistance per direction with their own unique resistor.  
As the wind vane rotates, a magnet closes the reed switches, and may close two at a time due to their proximity to each other also 16 different positions. Directions between, e.g. North East, are the resistance value of two resistors in parallel.  
Value ranges of the ADC determine the direction the wind.  

### DHT11: Measuring temperature and humidity
For recording temperature and humidity I’m using **DHT11** Temperature and Humidity Sensor.
Note: The DHT 11 I’ve been using include the internal 4.7k’s resistor.
It communicate with a ESP32 over a single wire and powered direct with 3.3V.
Powering ESP32 with 12V Power Source using Buck Converter

For the ESP32’s operating voltage, I’m using a buck converter LM2596 (step-down regulator) to safely bring 12V car battery down to 5V.

### 12V Car-battery Monitoring
I use the **INA226** DC current and power sensor to check the battery voltage.  
It provides accurate measurements of car-battery voltage, load voltage, current, and power.  
The INA226 has a voltage limit of 26 V and can measure a maximum current of ±3.2 A.  

![weather_station](https://github.com/user-attachments/assets/d8cf0e8d-2df1-443a-9cf3-b961a86efe49)

**ESP32 S2 mini** According to the datasheet you can find out which other GPIO pins can be used for projects.  

    GPIO03:  ADC Wind Direction
    GPIO37:  Rain Gauge
    GPIO39:  Anemometer (Wind speed)
    GPIO33:  SDA
    GPIO35:  SCL
    GPIO07:  DHT11
    GPIO05:  voltage divider (reserved)

> [!NOTE]
> For more information: [Weather-Station](https://forgani.com/electronics-projects/weather-station-home-assistant-esphome/).


