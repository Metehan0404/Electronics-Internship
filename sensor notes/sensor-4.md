# Sensor 4: KY-004 Tactile Button / SW Module

## Basic Information

- **Sensor name:** KY-004 Tactile Switch (Push Button)

- **Purpose:** Detecting user interaction by closing a digital circuit to send a signal to the microcontroller

- **Interface:** Digital Input (Pin 2)

- **Operating voltage:** 5V

- **Source / Reference:** Joy-IT Sensor Kit

## How it works
This sensor acts as a simple mechanical switch that allows or interrupts the flow of electricity when pressed.

- **Mechanism:** When the button is pressed, it completes the circuit (Closed). When released, the circuit remains open. In this setup, we use the Arduino's internal PULL-UP resistor.

- **Value Reading:** Due to the INPUT_PULLUP configuration, the digital pin reads 1 (HIGH) by default when the button is not pressed. When the button is pressed, the signal is pulled to ground, reading 0 (LOW).

- **Example Use:** User interfaces, reset switches, and mode selection in electronics.

## Hardware Setup
Jumper wires were used for connection to allow the button to be placed easily on the breadboard or moved as needed.

- **PIN Connection:** 
Arduino Uno (Joy-IT R3 DIP)

S (Signal / SW) → Digital Pin 2

(-) → GND

VCC (+) → 5V (Note: In PULLUP mode, only GND and Signal are strictly necessary)

- **Arduino Sketch:**

const int buttonPin = 2;

void setup() { 

  Serial.begin(9600);

  pinMode(buttonPin, INPUT_PULLUP); 

}

void loop() { 

  int buttonState = digitalRead(buttonPin);


  if (buttonState == LOW) { 

    Serial.println("Button Status: PRESSED");

  } else { 

    Serial.println("Button Status: RELEASED"); 
  }

  delay(100); 
  
}