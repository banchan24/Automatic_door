# Automatic_door
The goal of this project is to design and build an automatic door system using an Arduino microcontroller. The door opens automatically when the ultrasonic sensor detects a person standing within 0.05 m of the door. A visual indicator (LED) switches ON when the sensor detects a person at 0.15 m and remains illuminated until the door closes.--------------------------------------------------------------------------------------------------------------
Design:

<img width="1113" height="508" alt="image" src="https://github.com/user-attachments/assets/7f037b4f-3a04-49dd-9a6c-f41efe721d46" />

Components:
Servo 9 – A servo motor that physically opens and closes the door.

Ultrasonic Sensor – Detects distance by sending ultrasonic waves and timing the returning echo.

Push Button – Allows manual control to open or close the door.

LED Indicator – Lights up when the door opens and turns off once it closes.
--------------------------------------------------------------------------------------------------------------
How It Works
1. Idle State: Door stays closed, LED is off.
2. Approach Detected: If distance ≤ 0.15 m, the LED turns on.
3. Door Opens Automatically: If distance ≤ 0.05 m, the servo motor rotates to open the door.
4. Door Closes: After a short delay, the servo returns to the closed position and the LED turns off.
5. Manual Override: The push button can trigger the door to open/close at any time.
<img width="975" height="1030" alt="image" src="https://github.com/user-attachments/assets/afa84e74-d358-48ad-9158-bf83bf4cd61e" />

--------------------------------------------------------------------------------------------------------------
Distance Calculation

The ultrasonic sensor calculates distance based on the time taken for the sound wave to travel to the object and back:

<img width="957" height="60" alt="image" src="https://github.com/user-attachments/assets/65a683fe-eee9-4496-ad9c-6ec4c83ca0d0" />

In the code, this is simplified to:
<img width="390" height="44" alt="image" src="https://github.com/user-attachments/assets/6aa696b8-ba7a-4718-9d06-37cc6d0f79e7" />

≤ 0.05 m: Door opens and LED turns on.

≤ 0.15 m: LED turns on as an early indicator and stays lit until the door closes.


--------------------------------------------------------------------------------------------------------------
How to Use

1. Connect the components as defined in the code:

- Servo signal → pin 6

- Ultrasonic sensor TRIG → pin 4

- Ultrasonic sensor ECHO → pin 3

- LED → pin 2

- Button → pin 7

2. Upload the code to your Arduino board.

3. Open the Serial Monitor (9600 baud) to view distance readings.

4. Approach the door or press the button to see the automatic response.
--------------------------------------------------------------------------------------------------------------
Results

- The system correctly opened the door when a person was closer than 0.05 m.
- The LED illuminated when someone entered within 0.15 m and remained on until the door closed.
- Manual control via the push button worked as intended.

This project showcases a simple yet functional smart-door system built with Arduino.
By combining a servo motor, ultrasonic sensor, LED, and push button, it provides both automatic operation and manual control, making it a beginner-friendly example of integrating sensors and actuators for real-world automation.
