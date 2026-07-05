# July 2nd

I have designed the PCB for my Greenhouse monitor.
It includes:
- An ESP32-C3-WROOM-O2U to control the system
- An AP2112k-3.3 for regulating the 5V input to 3V3
- A 1x2 Screw Terminal to connect the solar power system
- A USB C Receptacle for uploading the program
- A JST_SH socket for connecting the temperature and humidity sensor
- A 1x3 header to connect the soil moisture sensor.

<img width="729" height="692" alt="image" src="https://github.com/user-attachments/assets/12714514-37b5-48bb-ae1f-71a5f5c7defb" />


# July 5th

I have improved upon my design as according to the reviewer.
I have:
- Moved the USB and JST_SH inputs closer to the edge of the board (There is no Shcottky diode on the USB input as i will not be plugging in both the solar and USB at the same time)
- Wired the USB D+ and D- pins differentially
- Connected the USB VBUS to the regulator
- Increased the size of the trace from the Screw Terminal to the Schottky diode.
- Added net labels for some nets

<img width="1311" height="1193" alt="image" src="https://github.com/user-attachments/assets/8c6494a4-dc74-4880-9d5f-68a61ebbc0dc" />
