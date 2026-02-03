# Sensor 6: KY-024 Linear Magnetic Hall Sensor

## Basic Information

- **Sensor name:** KY-024 Linear Magnetic Hall Sensor

- **Purpose:** Measuring the strength and polarity of a magnetic field.

- **Interface:** Analog Input (A3)

- **Operating voltage:** 5V

- **Source / Reference:** Joy-IT Sensor Kit

## How it works
This sensor utilizes the "Hall Effect," where a voltage difference is produced across an electrical conductor when a magnetic field is applied perpendicular to the current flow.

- **Mechanism:** The module features a linear Hall-effect device and a potentiometer to adjust sensitivity. Unlike simple magnetic switches, this version provides a continuous range of data.

- **Value Reading:** The output is an analog voltage that represents the magnetic flux density. The Arduino converts this into values from 0 to 1023. A neutral state (no magnet) usually sits around 512.

- **Example Use:** Speedometers, non-contact current sensing, and brushless motor controllers.

## Hardware Setup
Jumper wires were used to connect the sensor to the analog rail for precise data reading.

- **PIN Connection:** 
Arduino Uno (Joy-IT R3 DIP)

(+) → 5V

(-) → GND

A0 (Analog Out) → A3 (Analog Pin)

- **Arduino Sketch:**

const int hallAnalogPin = A3; 

void setup() {

  Serial.begin(9600);

  pinMode(hallAnalogPin, INPUT);

  Serial.println("Linear Hall Sensor Initialized...");

}

void loop() {

  int magneticValue = analogRead(hallAnalogPin);

  Serial.print("Magnetic Field Strength: ");

  Serial.println(magneticValue);

  if (magneticValue > 800 || magneticValue < 200) {

    Serial.println("-> STRONG MAGNETIC FIELD DETECTED!");

  }

  delay(300);
  
}