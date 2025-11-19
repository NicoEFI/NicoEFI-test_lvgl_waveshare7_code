# NicoEFI Test LVGL Waveshare 7" Code

This Arduino sketch demonstrates a five-point touch test with LVGL on a Waveshare 7" RGB LCD display using an ESP32-S3.

## Prerequisites

### LVGL Library Installation

This project requires the LVGL (Light and Versatile Graphics Library) to be installed. The library is not included in this repository due to its size.

**Installation Steps:**

1. **Using Arduino Library Manager (Recommended):**
   - Open Arduino IDE
   - Go to `Sketch` → `Include Library` → `Manage Libraries...`
   - Search for "lvgl"
   - Install "lvgl" by kisvegabor (version 8.3 or compatible)

2. **Manual Installation:**
   - Download LVGL from: https://github.com/lvgl/lvgl
   - Extract the downloaded archive
   - Rename the folder to `lvgl`
   - Copy the `lvgl` folder to your Arduino libraries directory:
     - Windows: `Documents\Arduino\libraries\`
     - macOS: `~/Documents/Arduino/libraries/`
     - Linux: `~/Arduino/libraries/`

3. **Configuration:**
   - The project includes `lv_conf.h` at the root level
   - This configuration file is already set up for the Waveshare display
   - No additional configuration changes should be needed

## Hardware Setup

- **Board:** ESP32-S3 (Waveshare ESP32-S3 RGB LCD)
- **Display:** 1024x600 RGB LCD (7 inch)
- **Touch Controller:** GT911 capacitive touch controller

## Library Structure

The project uses several custom drivers organized in Arduino-compatible library format:

- **waveshare_i2c**: I2C communication driver
- **waveshare_ioext**: IO extension chip driver (GPIO control via I2C)
- **waveshare_rgb**: RGB LCD panel driver
- **touch_common**: Common touch controller interface
- **touch_gt911**: GT911 touch controller driver
- **lvgl_port**: LVGL integration layer

## Compilation

1. Install LVGL library as described above
2. Open `test_lvgl_waveshare7_code.ino` in Arduino IDE
3. Select the ESP32-S3 board from Tools → Board menu
4. Compile and upload

## Features

- Double-buffered RGB LCD display
- Multi-touch support (up to 5 touch points)
- LVGL UI framework integration
- Custom UI screens (Logo and Menu)

## Notes

- The UI files (`ui_*.c`, `ui_*.h`) are auto-generated and should not be modified manually
- PSRAM is required and enabled by default for LVGL buffer allocation
- The display runs at 30MHz pixel clock with 1024x600 resolution
