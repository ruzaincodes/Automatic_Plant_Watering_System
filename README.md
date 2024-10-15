# Automatic Plant Watering System

## Overview

The **Automatic Plant Watering System** is a smart irrigation solution designed to automatically water your plants based on soil moisture levels. This project utilizes a soil moisture sensor to monitor the water content in the soil and controls a relay to activate the water pump when necessary.

## How It Works

The system operates by reading the output from a soil moisture sensor. When the sensor detects that the soil moisture is below a certain threshold, the system activates a relay to supply water to the plant. Conversely, if the soil moisture is sufficient, the relay is turned off, stopping the water supply.

### Key Components

- **Soil Moisture Sensor**: Monitors the moisture level of the soil.
- **Relay Module**: Controls the water pump based on the sensor readings.
- **Microcontroller (e.g., Arduino)**: Executes the code and manages the system's logic.

## Circuit Diagram

![Circuit Diagram](https://github.com/ruzaincooks/Automatic_Plant_Watering_System/blob/main/circuit.png)

## Code Explanation

Here is a breakdown of the code used in this project:

```cpp
int water; // random variable to store the sensor's output

void setup() {
  pinMode(3, OUTPUT); // Set pin 3 as output for relay board
  pinMode(6, INPUT);  // Set pin 6 as input for soil sensor
}

void loop() { 
  water = digitalRead(6);  // Read the signal from the soil sensor
  if(water == HIGH) { // If water level is full
    digitalWrite(3, LOW); // Turn off the relay
  } else {
    digitalWrite(3, HIGH); // Turn on the relay to supply water
  }
  delay(400); // Delay for 400 milliseconds before next reading
}
