# OLED Interfacing with Arduino UNO R4

This project demonstrates how to interface an SSD1306 OLED display with an Arduino UNO R4 WiFi microcontroller using I2C communication protocol.

## Project Overview

The application initializes a 128x64 OLED display and displays text on it. The OLED display communicates with the Arduino UNO R4 via I2C (TWI) protocol at address `0x3C`.

## Hardware Requirements

- Arduino UNO R4 WiFi board
- SSD1306 OLED Display (128x64 pixels)
- I2C communication pins (SDA and SCL)

## Software Dependencies

This project uses PlatformIO for build management and relies on the following libraries:

### Libraries
- **Adafruit GFX Library** (v1.12.4+) - Graphics library for drawing on displays
- **Adafruit SSD1306** (v2.5.16+) - Driver library for SSD1306 OLED displays

## Configuration

### main.cpp
The main application code initializes the display and writes text to it.

**Key Components:**
- **Screen Dimensions:** 128x64 pixels
- **Display Address:** 0x3C (I2C address)
- **Serial Baud Rate:** 9600 bps

**Functionality:**
1. Initializes serial communication at 9600 baud
2. Initializes the OLED display via I2C
3. Clears the display
4. Sets text color to white
5. Displays the message: "Hello, my name is slim shady"

### platformio.ini
Configuration file for PlatformIO build environment.

**Settings:**
- **Platform:** Renesas RA
- **Board:** UNO R4 WiFi
- **Framework:** Arduino
- **Monitor Speed:** 9600 baud
- **Monitor/Upload Port:** COM14 (adjust as needed for your system)

## Building and Uploading

1. **Build the project:**
   ```bash
   pio run
   ```

2. **Upload to board:**
   ```bash
   pio run -t upload
   ```

3. **Monitor serial output:**
   ```bash
   pio device monitor
   ```

## Wiring Diagram

Connect the OLED display to the Arduino UNO R4 as follows:

| OLED Pin | Arduino Pin |
|----------|------------|
| GND      | GND        |
| VCC      | 3.3V       |
| SDA      | SDA        |
| SCL      | SCL        |

## Troubleshooting

- **"OLED not found" message:** Verify the I2C address and wiring connections. The default address is `0x3C`.
- **Serial communication issues:** Ensure the monitor speed in `platformio.ini` matches the baud rate in the code (9600).
- **Port not found:** Update the `monitor_port` and `upload_port` settings in `platformio.ini` to match your system's COM port.

## Future Enhancements

- Add interactive graphics or animations
- Implement button input to control display content
- Add sensor data display
- Implement menu navigation

## References

- [Adafruit GFX Library Documentation](https://github.com/adafruit/Adafruit-GFX-Library)
- [Adafruit SSD1306 Library Documentation](https://github.com/adafruit/Adafruit_SSD1306)
- [Arduino I2C Documentation](https://www.arduino.cc/en/Reference/Wire)
- [PlatformIO Documentation](https://docs.platformio.org/)

