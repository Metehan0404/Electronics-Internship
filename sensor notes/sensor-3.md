# Sensor 3: KY-023 Dual-Axis Joystick Module

## Basic Information

- **Sensor name:** KY-023 Dual-Axis Joystick

- **Purpose:** Measuring directional movement along the X and Y axes using analog signals.

- **Interface:** Analog Input (A1, A2)

- **Operating voltage:** 5V

- **Source / Reference:** Joy-IT Sensor Kit

## How it works
This sensor consists of two potentiometers positioned perpendicularly to track movement in a 2D coordinate system.

- **Mechanism:** The joystick uses two 10k potentiometers for the X and Y axes. As the stick is moved, the resistance changes, varying the output voltage for each axis.

- **Value Reading:** The Arduino's ADC reads these voltages and converts them into digital values. In a 5V system, the range is 0 to 1023. The resting center point typically returns approximately 512 (half of 1023).

- **Example Use:** Remote-controlled vehicles, camera gimbal control, and gaming interfaces.

## Hardware Setup
Jumper wires were used to connect the module to ensure flexible positioning and stable signal transmission.

- **PIN Connection:** 
Arduino Uno (Joy-IT R3 DIP)

VRx (X-Axis) → A1 (Analog Pin)

VRy (Y-Axis) → A2 (Analog Pin)

+5V → 5V

(-) → GND

- **Arduino Sketch:**

const int pinX = A1;

const int pinY = A2;

void setup() {

  Serial.begin(9600);

  Serial.println("Joystick Axis Test Initialized...");

}

void loop() {

  int xValue = analogRead(pinX);

  int yValue = analogRead(pinY);

  Serial.print("X: ");

  Serial.print(xValue);

  Serial.print(" | Y: ");

  Serial.println(yValue);

  delay(200);
  
}
