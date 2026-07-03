# Solar-Powered Environmental & Soil Monitor

An ultra-low-power ESP32-C3 environmental telemetry node with solar harvesting and deep sleep optimization.

## Implementation, Topology, and Assembly Reference

The custom PCB routes the ESP32-C3-WROOM-02U peripherals to external components using these net configurations:
* **USB Native Data (-)**: GPIO18 (IO18) at J4 (A7/B7) for native flashing.
* **USB Native Data (+)**: GPIO19 (IO19) at J4 (A6/B6) for native flashing.
* **I2C Data (SDA)**: GPIO2 (IO2) at J2 (Pin 3) for the SHT41 sensor port.
* **I2C Clock (SCL)**: GPIO10 (IO10) at J2 (Pin 4) as an overridden clock channel.
* **Analog Soil Signal**: GPIO1 (IO1) at J3 (Pin 3) via ADC1_CH1 for 12-bit sampling.
* **Boot Mode Strap**: GPIO9 (IO9) at R1/R3 pulled to 3V3 with a 10k Ohm resistor for flash boot.

The power system regulates input voltages to protect the 6V-maximum AP2112K regulator and the ESP32-C3. A 9V 600mA solar panel feeds a Waveshare Power Manager to charge a 3.7V 1200mAh LiPo battery and supply a stable 5V 3A rail to PCB terminal J1. Current flows through an SS14L Schottky diode (D1)—dropping voltage to ~4.6V—before entering the AP2112K regulator (U1) to distribute a stable 3.3V power plane.

Verify the board assembly matches this functional checklist before power activation:
1. **Polarization (C1)**: The printed stripe on the Kyocera AVX Tantalum capacitor must face away from Ground and connect to the +5V rail.
2. **Directional Flow (D1)**: The printed cathode stripe on the SS14L Schottky diode must point toward the filtering capacitors (C1/C2) and away from the J1 input block.
3. **USB Verification**: Connecting J4 via a data-rated Type-C cable must natively enumerate an *ESP32-C3 USB Serial/JTAG Controller* without manual driver installation.
