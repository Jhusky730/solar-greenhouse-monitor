# Solar-Powered Backyard Greenhouse Monitor

This is an open-source, ultra-low-power garden station built to sit outside, soak up the sun, and keep tabs on soil moisture, air temperature, and humidity without needing anyone to swap out batteries or run extension cords into the dirt. 

The goal is a completely self-sufficient system that can handle the rainy UK weather and log data 24/7.

## How the Power Works (The Math)
* The Brain: Seeed Studio XIAO RP2040. It draws about 25mA while awake.
* Air Monitoring: Adafruit SHT41. Super efficient, drawing just 0.4 uA on average.
* Soil Monitoring: A capacitive v1.2 moisture probe. Draws about 5mA, but I am wiring it to a digital pin so I can turn it completely off between readings to save juice.
* The Battery: A 1200mAh PKCell LiPo battery. At a total system draw of ~30mA, it gives me roughly 40 hours of backup power if the sky turns pitch black.
* The Charger: A Waveshare Solar Manager board with built-in MPPT. It handles the 9V 600mA solar panel, drops the voltage down safely, and keeps the battery topped up after just 2-3 hours of good daylight.

## The Wiring Plan (For the Breadboard)
* Power Delivery: Waveshare 5V/GND Out goes straight to the outer power rails of the breadboard. The XIAO RP2040 gets its 5V and GND from these same rails.
* Adafruit SHT41 Air Sensor: 
  * VIN connects to Red Rail (+)
  * GND connects to Blue Rail (-)
  * SCL connects to XIAO Pin D5
  * SDA connects to XIAO Pin D4
* Capacitive Soil Sensor:
  * VCC connects to XIAO Pin D3 (Our software power switch)
  * GND connects to Blue Rail (-)
  * AOUT connects to XIAO Pin A0 (Analog read)

## Keeping It Safe Outside
* The main brain, charger, and LiPo battery live inside a sealed IP67 ABS plastic junction box.
* I am drilling holes for PG7 cable glands so the solar and soil cables can enter the box without letting rainwater or condensation leak in.
* The top electronics on the soil sensor will be sealed up tight with hot glue or silicone so the wet dirt doesn't short it out.
* The SHT41 sensor will sit inside a mini 3D-printed Stevenson screen (a slatted weather box) so the sun doesn't bake it and give fake temperature spikes.

