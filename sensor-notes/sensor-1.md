# Sensor 1: KY-011 2-Color LED Module

## Basic Information

- **Sensor name:** KY-011 2-Color LED Module

- **Purpose:** Visual status signaling (Red/Green)

- **Interface:** Digital output

- **Operating voltage:** 5V

- **Source / Reference:** Joy-IT Sensor Kit

## How it works
The KY-011 module contains a red and a green LED with a common cathode connection.

- **Mechanism:** Applying power to the signal pins lights up the respective LED.

- **Value Reading:** Controlled via digital signals; HIGH turns the LED on, LOW turns it off.

- **Example Use:** Status indicators for projects (e.g., can be used as a simple traffic light.).

## Hardware Setup
The sensor module was directly plugged into the Arduino Uno headers without using jumper wires.

- **PIN Connection** - Arduino Uno (Joy-IT R3 DIP)
G (Green) → Pin 12

R (Red) → Pin 13

- (GND) → GND

### Arduino Sketch

C++

void setup() {
  pinMode(12, OUTPUT); // Initialize pin 12 for Green LED
  pinMode(13, OUTPUT); // Initialize pin 13 for Red LED
}

void loop() {
  digitalWrite(12, HIGH); // Turn Green ON
  digitalWrite(13, LOW);  // Turn Red OFF
  delay(1000);            // Wait 1 second
  
  digitalWrite(12, LOW);  // Turn Green OFF
  digitalWrite(13, HIGH); // Turn Red ON
  delay(1000);            // Wait 1 second
}