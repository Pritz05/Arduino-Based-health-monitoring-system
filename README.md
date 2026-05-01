# L1 — Heart Rate & SpO2 Monitor

A compact Arduino Nano-based pulse oximeter and blood oxygen monitor with OLED display and button navigation.

---

## 📦 Components

| Reference | Component | Description |
|-----------|-----------|-------------|
| U_MCU | Arduino Nano v3.x | Main microcontroller |
| U1 | MAX30102_mod | Heart rate & SpO2 sensor (I2C) |
| U2 | SSD1306 | 128x64 OLED display (I2C) |
| SW1, SW2, SW3 | SW_Push | Tactile push buttons |
| C1, C2, C3 | 100nF capacitor | Button debounce capacitors |
| R1, R2, R3 | 1kΩ resistor | Button pull-up resistors |
| R4 | 1kΩ resistor | LED current limiting resistor |
| D1 | LED | Status indicator LED |

---

## 🔌 Pin Connections

| Arduino Pin | Connected To |
|-------------|--------------|
| A4 (SDA) | MAX30102 SDA, SSD1306 SDA |
| A5 (SCL) | MAX30102 SCL, SSD1306 SCL |
| A1 | Analog input (button or sensor) |
| D2–D13 | Available for button/LED assignment |
| +5V | VCC for all modules |
| GND | Common ground |

> **Note:** Both the MAX30102 and SSD1306 share the I2C bus (A4/A5). Their I2C addresses must be different (MAX30102: `0x57`, SSD1306: `0x3C` or `0x3D`).

---

## ⚡ Power

- Powered via USB through the Arduino Nano's onboard regulator
- All peripherals run on **+5V**
- Decoupling capacitors (100nF) on each button line for debounce

---

## 🛠️ Building & Flashing

### Requirements
- [Arduino IDE](https://www.arduino.cc/en/software) or PlatformIO
- Libraries:
  - `MAX3010x` (SparkFun or similar)
  - `Adafruit SSD1306`
  - `Adafruit GFX`

### Steps
1. Clone this repository
2. Open the sketch in Arduino IDE
3. Select **Board:** `Arduino Nano` and the correct **Port**
4. Install required libraries via Library Manager
5. Upload

---

## 📁 Repository Structure

```
├── L1.kicad_pro          # KiCad project file
├── L1.kicad_sch          # Schematic
├── L1.kicad_pcb          # PCB layout
├── L1.kicad_sym          # Custom schematic symbols
├── for_custom.pretty/    # Custom footprints
├── fp-lib-table          # Footprint library table
├── sym-lib-table         # Symbol library table
└── README.md
```

---

## 📐 PCB

Designed in **KiCad 9.0**.

> Gerber files and fabrication outputs can be found in the `/fab` directory (if included).

---

## 📄 License

MIT License — feel free to use, modify, and distribute.
