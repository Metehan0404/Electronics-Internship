# Project 1: Temperature-Controlled Alert System (Logic Implementation)

## Basic Information

- **Components Used:** KY-013 (Thermistor), KY-011 (LED)

- **Objective:** Implementing a decision-making logic using sensor data.

- **Operating voltage:** 5V

- **Source / Reference:** Joy-IT Sensor Kit

## How it works

- **Mechanism:** The system constantly monitors the ambient temperature. If the value crosses a predefined threshold, the system triggers a visual alert (LED).

- **Threshold Logic:** I defined a "normal" range based on the raw data (e.g., 713). Anything significantly above this is treated as a "High Temperature" event.

- **Conditional Execution:** Using the if-else statement, the Arduino processes the Input (A0) and determines the state of the Output (Pin 13).

## Hardware Setup

- **PIN Connection:** 
Arduino Uno (Joy-IT R3 DIP)

- **Temperature Sensor:** 

S (Signal) → A0 (Analog Pin)

Middle (+) → 5V

(-) → GND

- **LED Module:** 

R or G -> Pin 13 

(-) -> GND

- **Arduino Sketch:**

/*

  Temperature Alert System
  
*/

int tempPin = A0;

int ledPin = 13;

int threshold = 730;


void setup() {

  Serial.begin(9600);

  pinMode(ledPin, OUTPUT);

  Serial.println("Monitoring Temperature...");

}

void loop() {

  int rawValue = analogRead(tempPin);
  
  Serial.print("Current Value: ");

  Serial.println(rawValue);

  if (rawValue > threshold) {

    digitalWrite(ledPin, HIGH);

    Serial.println("!!! WARNING: HIGH TEMP !!!");

  } 

  else {

    digitalWrite(ledPin, LOW);

  }

  delay(5000); 
  
}
