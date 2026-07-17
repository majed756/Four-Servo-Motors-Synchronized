# Four-Servo-Motors-Synchronized
C++ embedded program for the Arduino Uno R3. It is designed to control four servo motors simultaneously

# 🤖 Synchronized 4-Servo Initialization Sequence

## 📌 Project Overview
The goal of this project is to initialize four servo motors with a smooth sweep from `0°` to `180°`, and then safely return them to a neutral `90°` resting position.

## 🛠️ Components & Wiring
This project was built and simulated using **Tinkercad**. 

* **Microcontroller:** Arduino Uno R3
*  4x Micro Servo Motors
*  1x Small Breadboard

## 🚀 How It Works (The Logic)
Unlike standard Arduino sketches that run continuously in the `loop()` function, this program leverages the `setup()` function to execute the movement sequence exactly once.
