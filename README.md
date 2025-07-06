## Servo Motor Control with Arduino Uno

This project demonstrates how to control **four servo motors** using an **Arduino Uno** board. The servo motors are connected to PWM pins D6, D9, D10, and D11.

### 🛠 Wiring Overview

- Servo 1 → D6  
- Servo 2 → D9  
- Servo 3 → D10  
- Servo 4 → D11  
- All servo motors share the **same power (5V)** and **ground (GND)** via a breadboard.

> **Note:** It is highly recommended to power the servo motors with an external 5V power supply, especially if you face jittering or limited movement.

### 🧠 Features

- All servos move together in a sweeping motion from 0° to 180° and back.
- Easily extendable to include individual control logic or sensors.

### 🔧 Libraries Used

- [Servo.h](https://www.arduino.cc/en/Reference/Servo) — Arduino built-in library for controlling servo motors.

---

## 💡 Circuit Diagram

![servo-arduino](<4-servo.png>)

---
### 🔧 Arduino Code

```cpp
#include <Servo.h>

// إنشاء كائنات السيرفو
Servo servo1;
Servo servo2;
Servo servo3;
Servo servo4;

void setup() {
  // ربط كل سيرفو بالمنفذ الخاص فيه
  servo1.attach(6);   // Servo 1 على D6
  servo2.attach(9);   // Servo 2 على D9
  servo3.attach(10);  // Servo 3 على D10
  servo4.attach(11);  // Servo 4 على D11
}

void loop() {
  // تحريك كل السيرفوهات من 0 إلى 180 درجة
  for (int angle = 0; angle <= 180; angle++) {
    servo1.write(angle);
    servo2.write(angle);
    servo3.write(angle);
    servo4.write(angle);
    delay(10);
  }

  // ثم الرجوع من 180 إلى 0 درجة
  for (int angle = 180; angle >= 0; angle--) {
    servo1.write(angle);
    servo2.write(angle);
    servo3.write(angle);
    servo4.write(angle);
    delay(10);
  }
}
```
### 📋 What the code does

- Moves 4 servo motors (D6, D9, D10, D11)
- Sweeps from 0° to 180° and back in sync
- Shows how to use `Servo.h` library with multiple motors

## 🚀 Getting Started

1. Connect the servo motors as shown.
2. Upload the Arduino sketch.
3. Watch all four motors rotate in sync!

