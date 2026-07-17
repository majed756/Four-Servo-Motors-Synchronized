# Four-Servo-Motors-Synchronized
C++ embedded program for the Arduino Uno R3. It is designed to control four servo motors simultaneously

# 🤖 Synchronized 4-Servo Initialization Sequence
<img width="1061" height="717" alt="image" src="https://github.com/user-attachments/assets/71a4c675-2d37-4e07-b8ef-9913e1fda6bd" />


## 📌 Project Overview
The goal of this project is to initialize four servo motors with a smooth sweep from `0°` to `180°`, and then safely return them to a neutral `90°` resting position.

## 🛠️ Components & Wiring
This project was built and simulated using **Tinkercad**. 

* **Microcontroller:** Arduino Uno R3
*  4x Micro Servo Motors
*  1x Small Breadboard

## 🚀 How It Works (The Logic)
Unlike standard Arduino sketches that run continuously in the `loop()` function, this program leverages the `setup()` function to execute the movement sequence exactly once.

1. **Initialization:** The servos are attached to pins 2, 3, 4, and 5.
2. **Forward Sweep:** A `for` loop smoothly drives all four motors from `0°` to `180°` with a `10ms` micro-delay between each degree for fluid motion.
3. **Return & Lock:** A second `for` loop drives the motors back from `180°` and stop exactly at `90°`.
4. **Idle State:** The `loop()` function is intentionally left empty. The microcontroller rests while the servos naturally hold their 90-degree position indefinitely.

 ## 💻 The C++ Code

```cpp
#include <Servo.h>

Servo servo1;
Servo servo2;
Servo servo3;
Servo servo4;

void setup() {
  servo1.attach(2);
  servo2.attach(3);
  servo3.attach(4);
  servo4.attach(5);

  //  Sweep from 0° to 180°
  for (int pos = 0; pos <= 180; pos += 1) { 
    servo1.write(pos);
    servo2.write(pos);
    servo3.write(pos);
    servo4.write(pos);
    delay(10); 
  }

  //  Sweep backward from 180° and stop EXACTLY at 90°
  for (int pos = 180; pos >= 90; pos -= 1) { 
    servo1.write(pos);
    servo2.write(pos);
    servo3.write(pos);
    servo4.write(pos);
    delay(10); 
  }
  
  
}

void loop() {
}
