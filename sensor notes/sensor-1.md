# Sensor 1: KY-011 2-Color LED Module

## Basic Information

- **Sensor name:** KY-011 2-Color LED Module

- **Purpose:** Visual status signaling (Red/Green)

- **Interface:** Digital output

- **Operating voltage:** 5V

- **Source / Reference:** Joy-IT Sensor Kit

## How it works (Test 1)
The KY-011 module contains a red and a green LED with a common cathode connection.

- **Mechanism:** Applying power to the signal pins lights up the respective LED.

- **Value Reading:** Controlled via digital signals; HIGH turns the LED on, LOW turns it off.

- **Example Use:** Status indicators for projects (e.g., can be used as a simple traffic light.).

## Hardware Setup
The sensor module was directly plugged into the Arduino Uno headers without using jumper wires.

- **PIN Connection:** 
Arduino Uno (Joy-IT R3 DIP)
G (Green) → Pin 12

R (Red) → Pin 13

(GND) → GND

- **Arduino Sketch**
void setup() {
  pinMode(12, OUTPUT);
  pinMode(13, OUTPUT);
}

void loop() {
  digitalWrite(12, HIGH);
  digitalWrite(13, LOW);
  delay(1000);
  
  digitalWrite(12, LOW);
  digitalWrite(13, HIGH);
  delay(1000);
}


## How it works (Test 2)
This experiment uses PWM to control the intensity of the LED, moving beyond simple ON/OFF states.

- **Mechanism:** Arduino flips the power on and off so incredibly fast (thousands of times per second) that our eyes cannot see the flickering. Instead, we see a "breathing" light.

- **Value Reading:** It is an output process. We send values between 0 (completely off) and 255 (maximum brightness).

- **Example Use:** "Standby" lights on laptops or smooth notification alerts.

## Hardware Setup
The sensor module was plugged into the Arduino Uno headers using jumper wires. For fading, pin 11 was used because we need PWM.

- **PIN Connection:** 
G (Green) → Pin 11 (PWM Pin)

(GND) → GND

- **Arduino Sketch**
int ledPin = 11;
int brightness = 0;
int fadeAmount = 5;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  analogWrite(ledPin, brightness);

  brightness = brightness + fadeAmount;

  if (brightness <= 0 || brightness >= 255) {
    fadeAmount = -fadeAmount;
  }

  delay(30);
}

