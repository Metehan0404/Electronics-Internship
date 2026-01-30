# Sensor 2: KY-001 Analog Temperature Sensor

## Basic Information

- **Sensor name:** KY-001 Analog Temperature Sensor

- **Purpose:** Measuring ambient temperature changes

- **Interface:** Analog Input (A0)

- **Operating voltage:** 5V

- **Source / Reference:** Joy-IT Sensor Kit

## How it works
This sensor operates as a Thermistor (NTC), which is a resistor that changes its electrical resistance based on the surrounding heat.

- **Mechanism:** The module uses a voltage divider circuit. As the temperature changes, the thermistor's resistance changes, which in turn changes the voltage sent to the Arduino.

- **Value Reading:** Arduino's ADC (Analog-to-Digital Converter) reads this incoming voltage and converts it into a digital value between 0 (0V) and 1023 (5V).

- **Example Use:** Digital thermometers, HVAC systems, and battery temperature monitoring.

## Hardware Setup
To ensure stable data and avoid pin mismatch, jumper wires were used for the connection instead of direct header plugging.

- **PIN Connection:** 
Arduino Uno (Joy-IT R3 DIP)

S (Signal) → A0 (Analog Pin)

Middle (+) → 5V

(-) → GND

- **Arduino Sketch:**

int tempPin = A0;

void setup() {

  Serial.begin(9600);

}

void loop() {

  int rawValue = analogRead(tempPin);
  
  Serial.print("Raw Value: ");

  Serial.println(rawValue);
  
  delay(5000);
  
}