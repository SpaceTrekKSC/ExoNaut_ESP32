# ExoNaut ESP32 Board

![ExoNaut Logo](https://via.placeholder.com/150)

A completely independent ESP32 board package for the Arduino IDE specifically designed for ExoNaut robotics projects. This package includes all necessary tools and components, eliminating the need to install the standard ESP32 core.

## Features

- Complete self-contained ESP32 development environment
- Optimized for ExoNaut robot projects
- Multiple CPU frequency options (80MHz, 160MHz, 240MHz)
- Flexible flash configuration options
- Adjustable upload speeds up to 921600 baud
- Configurable debug levels

## Installation

1. Open Arduino IDE
2. Go to **File > Preferences**
3. In the "Additional Board Manager URLs" field, add the following URL:
   ```
   [https://raw.githubusercontent.com/SpaceTrekKSC/ExoNaut_ESP32/main/package_exonaut_index.json](https://github.com/SpaceTrekKSC/ExoNaut_ESP32/raw/refs/heads/main/package_ExoNaut_index.json)
   ```
   (Multiple URLs can be separated by commas)
4. Click "OK" to save the preferences
5. Go to **Tools > Board > Board Manager**
6. Search for "ExoNaut"
7. Click "Install" on the "ExoNaut ESP32 Boards" package
8. After installation, select "ExoNaut_ESP32" from **Tools > Board > ExoNaut**

Note: This is a large package (~400MB) because it includes a complete toolchain and doesn't depend on other packages.

## Board Configuration

After selecting the ExoNaut_ESP32 board, you can configure various settings:

### CPU Frequency
- 240MHz (WiFi/BT) - Default, maximum performance
- 160MHz (WiFi/BT) - Balanced performance and power consumption
- 80MHz (WiFi/BT) - Lower power consumption

### Flash Mode
- QIO - Quad I/O (faster)
- DIO - Dual I/O (more compatible)

### Flash Frequency
- 80MHz - Faster flash access
- 40MHz - More compatible with various ESP32 modules

### Flash Size
- 4MB (32Mb) - Standard
- 8MB (64Mb) - Extended
- 16MB (128Mb) - Large capacity

### Upload Speed
- 921600 - Fastest, may be unstable on some computers
- 230400 - Good balance of speed and reliability
- 115200 - Most reliable, works with all setups

### Debug Level
- None - No debug output
- Error - Only error messages
- Warn - Errors and warnings
- Info - General information plus errors and warnings
- Debug - Detailed debugging information
- Verbose - All possible information

### Erase Flash
- Disabled - Normal upload
- Enabled - Erase all flash content before uploading

## Programming the ExoNaut_ESP32

1. Connect your ExoNaut device to your computer via USB
2. Select "ExoNaut_ESP32" from the Boards menu
3. Select the appropriate COM port
4. Configure board options as needed
5. Upload your sketch

## Package Details

This board package is completely independent from the standard ESP32 core and includes:

- Complete xtensa-esp32-elf compiler toolchain
- All necessary ESP32 libraries and core files
- Custom board definitions for ExoNaut hardware

The large package size allows for a standalone installation without dependencies on other packages.

## Sample Code

```cpp
// Basic ExoNaut Hello World example

void setup() {
  Serial.begin(9600);
  delay(1000); // Allow time for serial connection
  
  Serial.println("Hello ExoNaut!");
}

void loop() {
  Serial.println("ExoNaut is running...");
  delay(1000);
}
```

## Troubleshooting

### Upload Issues
- Make sure you have selected the correct COM port
- Try a lower upload speed (115200)
- Check USB cable connection
- Some ESP32 boards require pressing the BOOT button during upload

### Board Not Found
- Make sure the board is properly connected
- Some USB cables may not support data transfer
- Try installing the CP210x or CH340 drivers

### Installation Size
- The package is large (~400MB) due to inclusion of the complete toolchain
- Ensure you have sufficient disk space available

## Technical Information

This package includes:

- ESP32 Arduino core
- Xtensa ESP32 compiler toolchain (v14.2.0_20241119)
- esptool.py for uploading
- Complete ESP32 libraries collection

## Contributing

Contributions to improve the ExoNaut ESP32 board package are welcome! Please feel free to submit issues or pull requests.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- Based on ESP32 Arduino core
- Thanks to the Arduino and Espressif teams for their amazing work
- Special thanks to the ExoNaut team and community

---

For more information and updates, visit [our GitHub repository](https://github.com/SpaceTrekKSC/ExoNaut_ESP32).
