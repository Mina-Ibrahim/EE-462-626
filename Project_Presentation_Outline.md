# Presentation Outline

## 1. Title Slide
- Point-of-Care Patient Communication and Emergency Alert Prototype
- Names
- Course / program
- Date

## 2. Problem and Motivation
- Communication delay between patients and caregivers
- Need for structured health updates
- Importance of emergency alerts and acknowledgements
- Why this is relevant to embedded systems and healthcare

## 3. Project Objective
- Design a bedside communication prototype
- Allow patient to report symptoms or requests for help
- Send event to caregiver interface
- Receive acknowledgement or response
- Support emergency and urgent event handling

## 4. Proposed System Overview
- STM32 NUCLEO-F446RE as main controller
- ESP32 as wireless bridge
- OLED display and buttons for patient interaction
- Optional sensors for fall and temperature detection
- Laptop-based caregiver interface

## 5. Hardware Components
- STM32 NUCLEO-F446RE
- ESP32 module
- OLED display
- Buttons and emergency button
- Buzzer
- MPU6050 accelerometer
- Temperature sensor
- Breadboard and jumper wires

## 6. Patient Event Categories
- Pain
- Breathing difficulty
- Dizziness
- Assistance required
- Medication reminder
- Fever
- Fall detected
- Emergency button trigger
- Long inactivity

## 7. System Flow
1. Patient selects event
2. STM32 processes input and displays confirmation
3. Packet is formatted and sent to ESP32
4. ESP32 sends message wirelessly to caregiver interface
5. Caregiver acknowledges or replies
6. Patient receives response on OLED display

## 8. Design Features
- Event prioritization
- Structured packet format
- Timeout and retry logic
- Error detection/checksum
- State-machine menu system

## 9. Demonstration Plan
- Show normal event sending
- Show urgent event handling
- Show fall detection / emergency alert example
- Show response acknowledgement
- Show communication retry behavior

## 10. Challenges and Limitations
- Prototype only, not clinical-grade
- Limited sensor accuracy
- Wireless reliability issues
- Real-world safety constraints
- Scope must remain manageable

## 11. Future Work
- More sensors
- Better caregiver dashboard
- Improved fall detection logic
- Real-time logging and alert escalation
- Battery-powered version

## 12. Conclusion
- Prototype demonstrates embedded systems applied to healthcare communication
- Strong technical and practical value
- Clear path for expansion and improvement
