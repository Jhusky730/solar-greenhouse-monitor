# Solar ESP32-C3 Sensor

An ultra-low-power environmental monitor using an ESP32-C3 PCB. It harvests solar energy to track soil health, temperature, and humidity, then enters deep sleep.

---

## Hardware Used

* ESP32-C3-WROOM-02U Microcontroller
* AP2112K-3.3 Voltage Regulator
* HRO TYPE-C-31-M-12 USB-C Port
* Waveshare Solar Power Manager Module
* Solar Panel (9V 600mA)
* 3.7V 1200mAh LiPo Battery
* Adafruit SHT41 Temp/Humidity Sensor
* Capacitive Soil Moisture Sensor

---

## Pin Mapping

* USB D- -> Pin 11 (IO20)
* USB D+ -> Pin 12 (IO21)
* SHT41 SDA -> Pin 16 (IO2)
* SHT41 SCL -> Pin 3 (IO4)
* Soil Data -> Pin 4 (IO5)
* Soil Power Control -> Pin 15 (IO18)

---
