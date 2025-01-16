# ESP32 Microcontroller

## **How to Design a Custom ESP32 Board**

### **What is ESP32?**

The **ESP32** is a powerful, low-cost, Wi-Fi and Bluetooth-enabled microcontroller widely used for IoT, home automation, industrial automation, and sensor-based projects. It integrates both **Wi-Fi** and **Bluetooth** capabilities in a compact form, making it suitable for a variety of applications. The ESP32 is programmable via popular platforms like Arduino IDE and ESP-IDF, and it’s perfect for custom PCBs tailored to specific projects.

### **Components You'll Need**

Here are the essential components for designing a custom ESP32 board and their functions.

### **1. ESP32-S3-WROOM**

- **Role**: This module serves as the board's core processor, managing all processing tasks, Wi-Fi/Bluetooth communication, and GPIO control.
- **Key Points**:
    - It operates on 3.3V.
    - Includes GPIO pins for peripheral connections.
    - Comes with built-in flash memory for program storage.

---

### **2. USB-C Connector (4 Pins)**

- **Role**: Enables programming and power delivery to the ESP32.
- **Key Points**:
    - Includes VBUS (5V), GND, D+, and D- pins.
    - Used for USB data transfer and power input.
    - **Protection**: Add **5.1 kΩ pull-up resistors** to D+ and D- for proper USB enumeration.

---

### **3. Voltage Regulator (A1117-3.3)**

- **Role**: Converts the 5V USB input to 3.3V for ESP32 operation.
- **Key Points**:
    - Requires **22 µF capacitors** at the input and output for stabilization.
    - Connect the input pin (VIN) to USB-C VBUS (5V).
    - Output pin (VOUT) powers the ESP32.

---

### **4. Two Switch Buttons (EN and BOOT)**

- **Role**:
    - **EN**: Resets the ESP32.
    - **BOOT**: Enables bootloader mode for programming.
- **Key Points**:
    - EN pin is pulled HIGH via a **10 kΩ pull-up resistor** to 3.3V and connected to a switch for reset functionality.
    - BOOT pin (GPIO0) is pulled HIGH via a **10 kΩ pull-up resistor** to 3.3V and connected to a switch for bootloader mode.

---

### **5. Pin Headers**

- **Role**: Enable connections for programming and peripherals.
- **Key Points**:
    - Includes 6 pins: **VCC, GND, TX, RX, EN, and a GPIO pin** (e.g., GPIO36).
    - Use standard 2.54mm headers for easy connections.

---

### **6. Ground Plane**

- **Role**: Provides a common reference point for all ground connections through a continuous copper layer.
- **Key Points**:
    - Reduces noise and ensures stable operation.
    - Ensure it connects all GND pins from the USB-C, ESP32, capacitors, and voltage regulator.

---

### **7. Decoupling Capacitors**

- **Role**: Filter noise and stabilize power supply.
- **Key Points**:
    - Add **100 nF capacitors** close to the ESP32's 3.3V and GND pins.
    - Use **22 µF capacitors** for bulk decoupling at the voltage regulator's input and output.
