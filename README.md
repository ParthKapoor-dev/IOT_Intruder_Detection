### RFID Intruder Detection System with LCD and Motion Detection\*\*

---

#### **Project Overview**

This repository contains an Arduino-based intruder detection system that integrates **RFID authentication**, **motion detection**, and an **LCD display**. The system ensures secured access by authenticating users with an RFID card. If unauthorized motion is detected, the system raises an alarm. Additionally, the LCD provides real-time status updates.

---

### **Features**

- **RFID Authentication**:

  - Validates users with RFID cards.
  - Grants or denies access based on the card's unique ID.

- **Motion Detection**:

  - Monitors for motion using an ultrasonic sensor.
  - Triggers a buzzer alarm when unauthorized motion is detected.

- **LCD Display**:
  - Displays real-time messages like _"Access Granted"_, _"Access Denied"_, or _"Intruder Alert!"_.

---

### **Code Files**

1. **`lcd_display.ino`**

   - Manages the LCD interface for the system.
   - Displays messages based on RFID and motion detection statuses.
   - Key functionalities:
     - Displays _"Access Granted"_ or _"Access Denied"_ based on RFID authentication.
     - Displays _"Intruder Alert!"_ when motion is detected.

2. **`Motion_Detection.ino`**

   - Implements motion detection using an ultrasonic sensor.
   - Triggers the buzzer when unauthorized motion is detected within a predefined range.
   - Key functionalities:
     - Continuously monitors for motion.
     - Integrates seamlessly with RFID for decision-making.

3. **`RFID_Intruder_Detection.ino`**
   - Combines RFID authentication and motion detection.
   - Raises an alarm when unauthorized users attempt access or motion is detected.
   - Key functionalities:
     - Verifies RFID card IDs.
     - Activates buzzer and displays status messages on the LCD.

---

### **Hardware Requirements**

- **Arduino Board** (e.g., Uno, Mega, or NodeMCU)
- **RFID Module** (e.g., EM-18)
- **RFID Cards** or Tags
- **Ultrasonic Sensor** (e.g., HC-SR04)
- **LCD Display** (I2C-compatible, 16x2)
- **Buzzer**
- **Jumper Wires** and Breadboard

---

### **Wiring Diagram**

- **RFID Module**:
  - TX → Arduino RX or software serial pin
  - VCC → 3.3V/5V
  - GND → GND
- **Ultrasonic Sensor**:
  - Trig → Arduino digital pin
  - Echo → Arduino digital pin
  - VCC → 5V
  - GND → GND
- **LCD Display**:
  - SDA → A4 (on Uno) or SDA pin
  - SCL → A5 (on Uno) or SCL pin
  - VCC → 5V
  - GND → GND
- **Buzzer**:
  - Positive → Arduino digital pin
  - Negative → GND

---

### **Setup Instructions**

1. **Install Arduino Libraries**:

   - **LiquidCrystal_I2C**: For LCD integration.
   - **SoftwareSerial**: For RFID communication (if using software serial).
   - **DHT** (if applicable for advanced features).

2. **Upload Code**:

   - Select the appropriate `.ino` file based on functionality.
   - Open the Arduino IDE and upload the code to your board.

3. **Adjust Parameters**:
   - Replace placeholder RFID card IDs with your own.
   - Modify ultrasonic range thresholds in `Motion_Detection.ino` as needed.

---

### **How It Works**

1. **LCD Display (`lcd_display.ino`)**:

   - Shows system messages like _"System Ready"_, _"Access Granted"_, and _"Intruder Alert!"_.

2. **Motion Detection (`Motion_Detection.ino`)**:

   - Continuously monitors for motion.
   - If motion is detected, a buzzer alarm is activated.

3. **RFID Intruder Detection (`RFID_Intruder_Detection.ino`)**:
   - Checks the RFID card ID.
   - If the card is unauthorized or motion is detected, raises an alarm and displays a warning on the LCD.

---

### **Customization**

- **Change RFID Authentication**:
  - Edit the `authorizedCard` variable in `RFID_Intruder_Detection.ino`.
- **Modify Motion Range**:
  - Adjust `distance` thresholds in `Motion_Detection.ino` to set detection sensitivity.
- **LCD Messages**:
  - Customize messages in `lcd_display.ino`.

---

### **Applications**

- **Home Security**: Prevent unauthorized access to restricted areas.
- **Office Automation**: Secure entry points in offices.
- **Industrial Monitoring**: Protect sensitive equipment or facilities.

---

### **License**

This project is open-source and can be modified or distributed under the MIT License.

Let me know if you need further assistance!
