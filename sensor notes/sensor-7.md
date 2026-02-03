# Sensor 7: Hall Magnetic Field Sensor (Digital)

## Basic Information

- **Sensor name:** Digital Hall Effect Sensor

- **Purpose:** Detecting the presence or absence of a magnetic field (Binary sensing).

- **Interface:** Digital Input (Pin 4)

- **Operating voltage:** 5V

- **Source / Reference:** Joy-IT Sensor Kit

## How it works
Unlike the linear version, this sensor works as a digital switch triggered by magnetic flux.

- **Mechanism:** It contains a Hall-effect element that triggers a high/low state change when the magnetic field exceeds a certain threshold. It is either "On" or "Off."

- **Value Reading:** The output is a digital signal. When a magnet is brought close, the signal drops to LOW (0). When the magnet is removed, it returns to HIGH (1).

- **Example Use:** Laptop lid sensors (to sleep when closed), door/window security alarms, and bike speedometers.

## Hardware Setup
Jumper wires were used to connect the sensor to the analog rail for precise data reading.

- **PIN Connection:** 
Arduino Uno (Joy-IT R3 DIP)

S (Signal) → Digital Pin 4

(+) → 5V

(-) → GND

- **Arduino Sketch:**

const int hallDigitalPin = 4; 

void setup() {

  Serial.begin(9600);

  pinMode(hallDigitalPin, INPUT); 

  Serial.println("Digital Magnetic Sensor Initialized...");
  
}

void loop() {

  int magnetStatus = digitalRead(hallDigitalPin);

  if (magnetStatus == LOW) {

    Serial.println("Magnet: DETECTED");

  } else {

    Serial.println("Magnet: NOT DETECTED");

  }

  delay(200);
}