# BRACE - Gesture-Based Wearable Controller (ESP32 + MPU6050)

BRACE is a wearable hardware control system that translates wrist motion into digital commands.
It connects via Bluetooth and can act as a media controller, presentation remote, and PC input alternative.

## Competition Category
Hardware Control (Infomatrix)

## Features
- Wrist gesture detection (left/right swipe)
- Bluetooth HID control (media / keyboard commands)
- Baseline calibration (neutral wrist position at startup)
- Optional button for Play/Pause
- Designed for situations where touch is inconvenient (busy hands, gloves, injury, limited attention)

## Hardware
- ESP32 Dev Board (ESP32-WROOM-32)
- MPU6050 (GY-521)
- (Optional) Tactile Button + Slide Switch
- (Optional) Li-Po battery + TP4056 charging module

## Wiring
MPU6050 → ESP32:
- VCC → 3V3
- GND → GND
- SDA → GPIO 21
- SCL → GPIO 22

Button (optional):
- One leg → GND
- Other leg → GPIO 27 (INPUT_PULLUP)


## Software Setup
**Arduino IDE 2.x**
1. Install ESP32 boards: `esp32 by Espressif Systems`
2. Install libraries:
   - Adafruit MPU6050
   - Adafruit Unified Sensor
   - BleKeyboard (T-vK)

## How It Works
1. On startup, BRACE records the neutral wrist position (baseline).
2. MPU6050 provides gyroscope/accelerometer data.
3. Gesture algorithm compares live motion to baseline.
4. When threshold is reached, BRACE sends Bluetooth HID commands.

## Usage / Demo
1. Upload `BRACE` to ESP32
2. Pair Bluetooth device named **BRACE**
3. Test gestures:
   - Swipe right → Next track (or next slide)
   - Swipe left → Previous track (or previous slide)

## Future Extensions
- Smart home control (Home Assistant / BLE-to-phone automation)
- Air-mouse mode for PC cursor control
- Accessibility modes (slow gestures, tremor filtering)

## Team
ASA, Almaty "Bilim-Innovation" Lyceum, Almaty, Kazakhstan
