# Weekly Internship Log
This log tracks my daily progress and activities during the Electronics Internship.

## Week 1
### Day 1: 26/01/2026

* **Activities:** Learned the basic code for Arduino, tested the KY-011 2-Color LED Module with Arduino Uno (Joy-IT R3 DIP). Tried two different codes with the module and learned the basics of the code used for Arduino. Documented the hardware setup and pin connections.

* **Technical Skills Acquired:**

Installed the Arduino IDE and configured the necessary drivers for the microcontroller to be recognized by the OS.

Learned the difference between Digital Output (used for the LED) and Digital Input, and how the Arduino handles simple HIGH/LOW signals.

Understood the difference between digital and ground pins and how to read a sensor module's pinout (GND(-), R, G, S).

* **Observations:** 

Observed how the dual-color LED can switch between colors by activating different pins.

Realized that the code runs in a continuous loop; once the "Upload" is successful, the Arduino executes the instructions immediately and repeatedly.

Identified that while standard digital pins are sufficient for binary states, PWM pins can be utilized to simulate analog output for tasks requiring variable intensity.



### Day 2: 27/01/2026

* **Activities:** Focused on working with the KY-013 Temperature Sensor to monitor ambient heat changes. The goal was not just to read data, but to use that data to trigger a specific system response.

* **Technical Skills Acquired:**

Learned the difference between Digital Input/Output and Analog Output.

Understood how the Arduino processes variable voltage from a thermistor into a 10-bit digital range (0-1023).

Learned how to define "normal" vs. "critical" data ranges by analyzing real-time sensor output through the Serial Monitor.

* **Observations:** 

Noticed that the sensor reacts very quickly. Even touching it for a second changes the numbers on the screen immediately.

The 0 to 1023 range is very detailed. Makes it easy to pick a specific number to trigger the LED alert.

When trying to read the data too fast, the numbers jumped around. Adding a small delay made the readings much more stable.



### Day 3: 28/01/2026

* **Activities:** Integrated the KY-023 Dual-Axis Joystick and the KY-004 Tactile Button to explore complex input methods. The focus was on managing simultaneous analog data streams (X-Y axes) and implementing a digital trigger for user interaction.

* **Technical Skills Acquired:** 

Learned how to process multiple analog inputs concurrently without signal interference.

Understood the INPUT_PULLUP function, which utilizes the Arduino's internal resistor to ensure a stable "HIGH" state when a button is not pressed.

Learned how to translate mechanical movement (joystick tilt) and momentary contact (button press) into actionable software commands.

* **Observations:** 

Observed that while the theoretical center is 512, the mechanical resting position of the joystick can vary slightly, requiring a "deadzone" in code for precise control.

Noticed that using PULLUP logic means the button returns a 0 (LOW) when active; this reversed logic is crucial for correct conditional programming.

Confirmed that the X and Y potentiometers operate independently, allowing for diagonal movement tracking by calculating the relationship between both values.





### Day 4: (29/01/2026)

* **Activities:** Created the official GitHub repository for the internship. Installed and learned the basic GitHub Desktop workflow (Clone, Commit, Push). Created the needed folders, Converted all previously written reports to markdown versions and pushed them to Github.

* **Technical Skills Acquired:** 

Learned how to use GitHub and how to interact with it as I need.

Learned what "Markdown" or ".md" texts are and how to write them.


* **Observations:** None



### Day 5: 30/01/2026

* **Activities:** Implemented the HC-SR04 Ultrasonic Distance Sensor to measure object proximity. The objective was to convert raw timing data into physical distance (centimeters) using mathematical constants.

* **Technical Skills Acquired:** 

Learned to use the pulseIn() function to capture the precise microsecond duration of a reflected sound wave.

Applied the speed of sound constant (0.034 cm/μs) to derive distance, understanding why the result must be divided by 2 (to account for the out-and-back path).

Mastered the logic of manually toggling a trigger pin to initiate a sensor reading.

* **Observations:** 

Noticed that soft or angled surfaces (like fabric) can absorb or deflect sound waves, leading to occasional "ghost" readings or inaccuracies.

Confirmed that the sensor provides highly stable readings for flat, solid objects within a 2 cm to 400 cm range.

Observed that adding a small delay() is necessary to prevent the outgoing sound pulses from interfering with the previous echoes.



### Day 6: 31/01/2026

* **Activities:** Integrated the KY-024 Linear Magnetic Hall Sensor to explore electromagnetic field detection. The goal was to move beyond simple "on/off" detection and measure the varying intensity of a magnetic field based on proximity and polarity.

* **Technical Skills Acquired:** 

Learned how a Hall Effect sensor converts magnetic field strength into a linear voltage range, allowing for distance-based sensing rather than just binary detection.

Practiced setting software thresholds to distinguish between ambient magnetic noise and the deliberate presence of a magnet.

Observed how the analog values react differently depending on which pole (North or South) of the magnet is facing the sensor.

* **Observations:** 

Noticed that the sensor is highly sensitive to distance; even a few millimeters of movement caused significant shifts in the 0–1023 analog range.

Identified that without a magnet nearby, the sensor stabilizes at a "resting" value (roughly 512), representing a zero-field state.

Observed that electronic devices nearby (like smartphone speakers) can cause minor fluctuations in the readings, highlighting the importance of shielding in precise projects.



### Day 7: 01/02/2026

* **Activities:** Tested and implemented the Digital Hall Effect Sensor to understand binary magnetic sensing. The objective was to create a contactless switch mechanism that triggers based on the presence of a magnetic field.

* **Technical Skills Acquired:** 

Mastered the use of digitalRead() to detect physical presence without mechanical wear, utilizing the Hall effect as a digital trigger.

Learned how to distinguish between "On" (Detected) and "Off" (Not Detected) states to automate responses, such as simulated security alerts.

Verified the difference between analog fluctuation and the clean, latching signal of a digital Hall module.

* **Observations:** 

Observed that the sensor has a specific "activation point"; the signal only flips to LOW when the magnet reaches a precise distance, providing a very reliable trigger.

Noticed that some digital Hall sensors are unipolar, meaning they only react to one specific side (pole) of the magnet, which is a critical factor for installation.

Confirmed that because there are no moving parts involved in the sensing, this method is superior to mechanical limit switches for long-term use in dusty or high-vibration environments.