## Abstract: 
This project presents a Smart Safety Jacket, an IoT-based wearable device designed to enhance 
the safety and independence of elderly individuals. The system integrates a pulse oximeter 
(MAX30100) for monitoring oxygen saturation and heart rate, an accelerometer (MPU6050) 
for fall detection, and a voice playback system (DFPlayer Mini) for navigation assistance. A 
memory button triggers voice guidance to aid users with memory loss, while Bluetooth Low 
Energy (BLE) communication enables real-time alerts to caregivers via a mobile app. The 
ESP32 microcontroller processes sensor data and manages system operations. A 16x2 LCD 
displays health status, and a green/red LED indicates safe or emergency states. This project 
offers a cost-effective, scalable solution for elderly care, suitable for home and outdoor use. 
## Introduction: 
The aging population faces significant challenges, including health emergencies (e.g., low 
oxygen levels, falls) and memory-related issues (e.g., dementia), which can compromise safety 
and independence. Traditional wearables like smartwatches often lack integrated navigation 
support or automated emergency alerts tailored for elderly needs. This project proposes a Smart 
Safety Jacket, an IoT-based system that monitors health parameters, detects falls, provides 
navigation cues, and communicates alerts using BLE technology. The system uses affordable 
components, including an ESP32 microcontroller, MAX30100 pulse oximeter, MPU6050 
accelerometer, DFPlayer Mini for voice playback, and a 16x2 LCD for real-time display. The 
jacket empowers elderly users to navigate confidently while ensuring rapid caregiver response 
during emergencies, making it ideal for healthcare, home automation, and assisted living 
applications. 
Components Used in Smart Safety Jacket 
1. ESP32 Microcontroller 
Function: The ESP32 serves as the central processing unit, collecting data from sensors, 
processing it, triggering voice playback, and sending alerts via BLE to a mobile app. 
Features: 
 Dual-core processor, built-in Wi-Fi/Bluetooth 
 Multiple interfaces (GPIO, I2C, SPI) 
 Python/C++ programming support 
2. MAX30100 Pulse Oximeter Sensor 
Function: Measures oxygen saturation (SpO2) and heart rate non-invasively using infrared and 
red LEDs. 
Specifications: 
 SpO2 Range: 0% to 100% (±2% accuracy) 
 Heart Rate Range: 30-240 bpm (±2 bpm accuracy) 
 Operating Voltage: 3.3V 
 Communication: I2C interface 
3. MPU6050 Accelerometer 
Function: Detects sudden falls by analyzing motion patterns, triggering emergency alerts. 
Specifications: 
 Accelerometer Range: ±2g to ±16g 
 Operating Voltage: 3.3V 
 Communication: I2C interface 
4. DFPlayer Mini (Voice Playback Module) 
Function: Plays pre-recorded voice messages for navigation guidance when the memory button 
is pressed. 
Specifications: 
 Audio Format: MP3/WAV 
 Operating Voltage: 3.3V-5V 
 Interface: Serial communication 
5. Memory Button 
Function: A tactile button stitched into the jacket to trigger voice guidance for navigation. 
Specifications: 
 Type: Push-button switch 
 Operating Voltage: 3.3V 
6. 16x2 LCD Display (With I2C Module) 
Function: Displays real-time health data (SpO2, heart rate, system status). 
Specifications: 
 Display: 16 characters per row, 2 rows 
 Operating Voltage: 5V 
 Interface: I2C 
7. LED Indicators (Green and Red) 
Function: Green LED indicates a safe state (no anomalies); red LED signals an emergency 
(e.g., low SpO2, fall). 
Specifications: 
 Operating Voltage: 3.3V 
 Type: Standard 5mm LEDs 
8. Speaker 
Function: Outputs voice guidance messages from the DFPlayer Mini. 
Specifications: 
 Size: Small, collar-mounted 
 Operating Voltage: 3.3V-5V 
9. Connecting Wires & Breadboard 
Function: Facilitates electrical connections between the ESP32 and other components. 
10. Power Supply (3.7V Li-ion Battery) 
Function: Powers the system with a rechargeable battery for portability. 
11. Arduino IDE and Libraries (Software Component) 
Function: The system uses C++ code in the Arduino IDE to read sensor data, process it, and 
manage outputs. Libraries include Wire.h (I2C), MAX30100_PulseOximeter.h, MPU6050.h, 
and DFPlayer_Mini_Mp3.h. 
## Working of Smart Safety Jacket 
Step 1: System Initialization 
 The ESP32 is powered on and runs a C++ program. 
 Libraries (e.g., Wire.h, MAX30100_PulseOximeter.h) are initialized to communicate 
with sensors, LCD, and DFPlayer Mini. 
 The green LED is turned on to indicate a safe state. 
Step 2: Sensor Data Collection 
 The MAX30100 sensor measures oxygen saturation and heart rate using optical 
sensing. 
 The MPU6050 accelerometer monitors motion to detect falls based on sudden changes 
in acceleration. 
 The ESP32 reads data via I2C and GPIO interfaces. 
Step 3: Data Processing 
 The ESP32 processes raw sensor data, converting it into readable values (e.g., SpO2 %, 
heart rate bpm). 
 Conditional checks filter out erroneous data (e.g., SpO2 < 90%, heart rate < 60 or > 100 
bpm, fall detected). 
 The system logs data for potential analysis. 
Step 4: Navigation Assistance 
 When the memory button is pressed, the DFPlayer Mini plays a pre-recorded voice 
message (e.g., “You are going to the park”) via the speaker. 
 The ESP32 monitors button input via GPIO. 
Step 5: Displaying Data on 16x2 LCD 
 Health data (SpO2, heart rate) and system status are displayed on the LCD using I2C 
communication. 
 The LCD updates every few seconds. 
Step 6: Emergency Alerts 
 If anomalies are detected (e.g., SpO2 < 90%, fall), the red LED turns on, and the green 
LED turns off. 
 The ESP32 sends an alert via BLE to a paired smartphone app, including health data 
and location (if GPS is added). 
 A buzzer (optional) can sound to alert nearby individuals. 
Step 7: Continuous Monitoring 
 The system runs in a loop, continuously monitoring sensors and responding to butt
