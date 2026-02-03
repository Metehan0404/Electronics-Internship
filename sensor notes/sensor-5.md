# Sensor 5: HC-SR04 Ultrasonic Distance Sensor

## Basic Information

- **Sensor name:** HC-SR04 Ultrasonic Distance Sensor

- **Purpose:** Measuring the distance to an object by using ultrasonic sound waves.

- **Interface:** Digital Input/Output (Trig & Echo pins)

- **Operating voltage:** 5V

- **Source / Reference:** Joy-IT Sensor Kit

## How it works
This sensor works on the principle of "Echolocation," similar to how bats or dolphins navigate.

- **Mechanism:** The sensor has two main parts: a transmitter (Trigger) and a receiver (Echo). The transmitter sends out a high-frequency sound pulse. When this pulse hits an object, it bounces back to the receiver.

- **Value Reading:** The Arduino measures the time it takes for the pulse to return. Using the speed of sound, it calculates the distance using the formula: Distance = (Time*0.034) / 2.

- **Example Use:** Reverse parking sensors in cars, liquid level monitoring in tanks, and obstacle avoidance in robotics.

## Hardware Setup
Since this sensor requires 4 pins, jumper wires were used to connect it to the digital rail of the Arduino.

- **PIN Connection:** 
Arduino Uno (Joy-IT R3 DIP)

VCC → 5V

Trig → Digital Pin 9

Echo → Digital Pin 10

(-) → GND

- **Arduino Sketch:**

const int trigPin = 9;

const int echoPin = 10;

void setup() { 

  Serial.begin(9600); 

  pinMode(trigPin, OUTPUT); 

  pinMode(echoPin, INPUT); 

  Serial.println("Ultrasonic Distance Sensor Initialized..."); 

}

void loop() { 

  digitalWrite(trigPin, LOW);

  delayMicroseconds(2);

  digitalWrite(trigPin, HIGH);

  delayMicroseconds(10);

  digitalWrite(trigPin, LOW);

  long duration = pulseIn(echoPin, HIGH);

  int distance = duration * 0.034 / 2;

  Serial.print("Distance: "); 

  Serial.print(distance); 

  Serial.println(" cm");


  delay(200); 
  
}