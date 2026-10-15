# Point-of-Care Patient Communication and Emergency Alert Prototype

## 1. Introduction

Communication between patients and healthcare providers is a critical part of effective care. In many clinical settings, patients may need to communicate pain, breathing problems, dizziness, falls, medication concerns, or requests for assistance. Traditional communication methods can be slow, inconsistent, or difficult to organize, especially when nurses or doctors are busy.

This project proposes the development of a point-of-care communication prototype that allows a patient to report important health-related events using a simple embedded device. The system uses an STM32 NUCLEO-F446RE as the main controller and an ESP32 as a wireless communication bridge. The patient interacts with the device through a small OLED display and physical buttons. The system organizes the patient’s inputs into a structured message and sends it to a caregiver or doctor interface for review and response.

The system is designed as a prototype that demonstrates how embedded technology can support patient communication in clinical environments. It does not attempt to diagnose medical conditions or replace professional healthcare equipment. Instead, it focuses on structured symptom reporting, caregiver acknowledgement, emergency-event detection, and communication reliability.

---

## 2. Problem Statement

Patients in healthcare environments often need to communicate urgent or non-urgent information to caregivers quickly and clearly. Common issues may include pain, respiratory distress, dizziness, medication concerns, poor mobility, or fall events. Without a structured communication system, these reports may be delayed, misunderstood, or inconsistent.

The problem addressed by this project is therefore: how can an embedded system be designed to allow a patient to report structured health information and emergency events reliably to a caregiver or doctor while also supporting acknowledgement and response?

This project proposes a practical embedded system solution that focuses on patient communication, event reporting, and communication reliability. The device will provide a simple interface for the patient to input information, display their selected data on an OLED screen, format a communication packet, and transmit it wirelessly to a caregiver device.

---

## 3. Proposed System

The proposed system is a bedside patient communication and emergency alert prototype. It consists of the following major components:

1. Patient input module
   - Buttons for navigation and selection
   - Optional emergency button
   - Optional sensor-based detection

2. STM32 processing unit
   - Main controller
   - Reads buttons and sensor values
   - Controls OLED output
   - Builds structured communication packets
   - Manages timeout, retry, and acknowledgement logic

3. Wireless communication bridge
   - ESP32 handles Wi-Fi communication
   - Sends data to the caregiver/doctor interface
   - Receives acknowledgement or response message from the caregiver side

4. Caregiver interface
   - Laptop or computer interface
   - Displays patient message, event type, severity, and timestamp
   - Allows a caregiver to send a response back to the patient

5. Patient response display
   - Patient receives an acknowledgement or instruction on the OLED display

This prototype is intended to demonstrate dependable embedded communication, structured event reporting, and basic emergency response logic in a point-of-care setting.

---

## 4. Best Practical Events to Detect and Report

The system will prioritize events that are highly relevant to patient communication and bedside care. The following event types are considered practical and valuable for a prototype:

- Fall or sudden impact
- Pain level or pain location
- Shortness of breath / breathing difficulty
- Feeling faint or dizzy
- Need for assistance / help call
- Missed medication / medication reminder
- Fever / temperature abnormality
- Weakness or inability to move
- Emergency button pressed
- Long inactivity / no response for some time

These events can be handled as either routine reports or emergency alerts depending on severity. A priority system can be implemented so that falls, breathing problems, or emergency button presses receive higher priority than routine status updates.

---

## 5. Objectives

The primary objective of the project is to create a functional point-of-care prototype that demonstrates reliable patient-to-caregiver communication and emergency event reporting.

The specific objectives are:

- Use the STM32 NUCLEO-F446RE as the main control unit
- Implement a menu-based user interface using buttons and an OLED display
- Allow the patient to report health-related issues or events
- Track patient events such as pain, dizziness, shortness of breath, assistance requests, falls, and fever
- Collect optional sensor information such as motion and temperature
- Format the patient’s report into a structured communication packet
- Transmit the message from the STM32 to the ESP32 using UART
- Send the message wirelessly to a caregiver device or laptop interface
- Receive acknowledgement or response messages
- Display caregiver responses back to the patient on the OLED screen
- Implement timeout, retry, and error-handling logic
- Demonstrate a practical embedded point-of-care prototype

---

## 6. Proposed Major Features

### 6.1 Patient Input Interface
The patient will interact with the system using:

- Up button
- Down button
- Select button
- Back button
- Emergency button (optional but recommended)

A small OLED screen will show the menu and message states.

### 6.2 Event Menu System
The menu will allow selection of the following categories:

- Pain
- Breathing problem
- Dizziness
- Need assistance
- Temperature concern
- Medication reminder
- Fall detected
- Emergency call
- No response / inactivity

A simple state machine will manage transitions between menu states and event reporting.

### 6.3 Structured Communication Packet
Messages should be stored as structured packets rather than simple ASCII text only. Example fields include:

- Message ID
- Event Type
- Severity Level
- Location
- Time Stamp
- Optional Sensor Value
- Checksum

Example packet:

- ID = 27
- TYPE = FALL
- SEVERITY = HIGH
- TIME = 10:42:15
- SENSOR = ACCELEROMETER_TRIGGER
- CHECKSUM = VALID

This allows the system to be more robust and professional.

### 6.4 ESP32 Wireless Bridge
The ESP32 will act as the communication bridge between the patient device and the laptop/doctor interface. The STM32 communicates with the ESP32 over UART, and the ESP32 sends the event over Wi-Fi to the caregiver device.

### 6.5 Caregiver Interface
The caregiver interface can be implemented on a laptop as a simple monitoring dashboard. It will display:

- Event type
- Severity
- Time received
- Patient ID or room number
- Acknowledge button
- Response message option

### 6.6 Error Handling and Reliability
Reliability is a critical part of the project. The system will include:

- Timeout waiting for acknowledgement
- Message retry if no response is received
- Checksum or CRC validation
- Event confirmation on OLED display
- Error message if communication fails

---

## 7. Hardware Components

The following hardware is recommended for the prototype. A practical and achievable list is given below.

### Core Required Hardware

| Component | Quantity | Purpose | Suggested link |
|---|---:|---|---|
| STM32 NUCLEO-F446RE | 1 | Main embedded controller | Digikey: https://www.digikey.com/en/products/filter/development-boards-kits-programmers/277?keywords=NUCLEO-F446RE |
| ESP32 Development Board | 1 | Wireless communication bridge | DigiKey: https://www.digikey.com/en/products/filter/development-boards-kits-programmers/277?keywords=ESP32%20devkit |
| SSD1306 OLED Display | 1 | Patient display output | DigiKey: https://www.digikey.com/en/products/filter/display-modules/1210?keywords=ssd1306 |
| Push Buttons | 4 | Menu navigation and selection | DigiKey: https://www.digikey.com/en/products/filter/switches/139?keywords=push%20button%20switch |
| Emergency Button | 1 | Direct emergency call | DigiKey: https://www.digikey.com/en/products/filter/switches/139?keywords=emergency%20button |
| Buzzer | 1 | Alert and acknowledgement tones | DigiKey: https://www.digikey.com/en/products/filter/audio-devices/170?keywords=buzzer |
| Breadboard | 1 | Prototyping | DigiKey: https://www.digikey.com/en/products/filter/prototyping-products/235?keywords=breadboard |
| Jumper Wires | 1 set | Wiring connections | DigiKey: https://www.digikey.com/en/products/filter/wire-harnesses/484?keywords=jumper%20wire%20male%20female |
| Resistors | Several | Pull-ups, current limiting | DigiKey: https://www.digikey.com/en/products/filter/resistors/54?keywords=10k%20resistor |
| USB Cables | 1–2 | Programming and power | DigiKey: https://www.digikey.com/en/products/filter/cables-wires/158?keywords=usb%20micro%20cable |

### Recommended Sensor Hardware

| Component | Quantity | Purpose | Suggested link |
|---|---:|---|---|
| MPU6050 Accelerometer/Gyroscope | 1 | Fall detection and sudden impact sensing | DigiKey: https://www.digikey.com/en/products/filter/sensors-transducers/196?keywords=mpu6050 |
| TMP117 or LM35 Temperature Sensor | 1 | Fever / abnormal temperature detection | DigiKey: https://www.digikey.com/en/products/filter/sensors-transducers/196?keywords=TMP117 |
| MAX30102 Pulse Sensor | 1 | Optional heart rate / pulse monitoring | DigiKey: https://www.digikey.com/en/products/filter/sensors-transducers/196?keywords=MAX30102 |
| RTC Module | 1 | Event timestamp logging | DigiKey: https://www.digikey.com/en/products/filter/clock-timing-real-time-clocks/274?keywords=RTC%20module |

### Amazon Alternative Search Links

For convenience, the same parts can also be found through Amazon search pages:

- STM32 NUCLEO-F446RE: https://www.amazon.com/s?k=STM32+NUCLEO+F446RE
- ESP32 DevKit: https://www.amazon.com/s?k=ESP32+DevKit
- SSD1306 OLED: https://www.amazon.com/s?k=SSD1306+OLED
- MPU6050: https://www.amazon.com/s?k=MPU6050+accelerometer
- TMP117 / LM35: https://www.amazon.com/s?k=temperature+sensor+TMP117
- MAX30102: https://www.amazon.com/s?k=MAX30102+sensor
- Buzzer: https://www.amazon.com/s?k=electronic+buzzer
- Breadboard and jumper wires: https://www.amazon.com/s?k=breadboard+jumper+wires

> Note: These are search links rather than exact vendor-specific product pages. Exact part variants should be checked before purchasing to ensure compatibility with the STM32 and ESP32.

---

## 8. Suggestions and Improvements

The following improvements are recommended to strengthen the project:

1. Add fall detection using an accelerometer
   - This gives the project a clear, meaningful emergency feature.
   - It demonstrates practical embedded sensor logic.

2. Add a dedicated emergency button
   - This represents a direct patient safety trigger.
   - It is a simple but highly valuable addition.

3. Use a priority-based alert system
   - Emergency > urgent > routine
   - This makes the system feel realistic and useful.

4. Add timestamping for every event
   - This is important for tracking when a patient reported an issue.

5. Add retries and acknowledgement logic
   - This improves communication reliability.

6. Use structured packet definitions
   - Event type, severity, ID, timestamp, checksum
   - This is more professional than only sending text.

7. Use a simple caregiver dashboard
   - A monitor or laptop interface is sufficient for the prototype.

8. Keep the project focused on a usable MVP
   - Core features should work reliably before adding extra sensors.

9. Treat sensors as optional and stretch goals
   - Temperature and accelerometer are valuable, but the main project should not depend on too many sensors at first.

10. Include a clear limitation statement
   - The project is a prototype, not a diagnosis or medical device.

---

## 9. Requirements to Make the Project Strong

### Functional Requirements
- Patient can select a health-related event
- Device displays confirmation and status
- Message is transmitted to the caregiver interface
- Acknowledgement is received and shown to the patient
- Emergency or fall events are prioritized
- Sensor data can be added without breaking the main communication path

### Technical Requirements
- GPIO for buttons and buzzer
- I2C for OLED display
- UART between STM32 and ESP32
- State machine architecture for menu and event flow
- Reliable packet formatting and parsing
- Timeout and retry logic
- Basic checksum or data validation

### Non-Functional Requirements
- Easy to use
- Clear display
- Reliable transmission
- Real-time response
- Moderate complexity that is achievable within the project timeline
- Good documentation and testing

---

## 10. Development Plan

### Phase 1: Core Hardware and Setup
- Configure STM32 with the NUCLEO-F446RE
- Test GPIO for buttons
- Test OLED display communication over I2C
- Confirm UART communication with ESP32

### Phase 2: Menu and State Machine
- Create menu states for patient events
- Add button navigation logic
- Add confirmation and invalid input handling

### Phase 3: Event Detection and Reporting
- Add pain, breathing, dizziness, assistance, and medication events
- Add emergency event handling
- Add priority and severity logic

### Phase 4: Sensor Integration
- Add MPU6050 for fall detection
- Add temperature sensor for fever monitoring
- Add basic thresholds and alert triggering

### Phase 5: Wireless Communication and Caregiver Interface
- Send the message to the caregiver laptop
- Receive acknowledgement or response
- Display caregiver response on patient OLED

### Phase 6: Testing and Validation
- Test normal use cases
- Test fall/emergency cases
- Test timing out and retry logic
- Test communication failure behavior
- Validate packet integrity and acknowledgement flow

---

## 11. Risk and Design Considerations

The main engineering risks are:

- Reliable UART communication between STM32 and ESP32
- Debugging wireless messages during testing
- Sensor false positives for fall detection
- Menu complexity increasing beyond the project scope
- Time limit for full implementation and testing

These risks can be controlled by keeping the prototype focused, limiting the number of sensors, and using a clear state-machine structure.

---

## 12. Conclusion

This project is a strong embedded systems proposal because it combines practical healthcare communication, real hardware, wireless communication, state-machine design, sensor integration, and reliability testing. It is particularly suitable as a point-of-care prototype because it focuses on patient feedback, caregiver awareness, and structured communication rather than direct medical diagnosis.

The ideal version of the project should focus on a clear patient workflow and a limited but effective event set, with fall detection, emergency button support, and message acknowledgement as core features. If implemented carefully, this system can become an impressive and demonstrable proof-of-concept for embedded point-of-care communication.

---

## 13. Recommended Final Project Direction

The final project should be framed as:

"A bedside patient communication and emergency alert prototype for structured symptom reporting and caregiver acknowledgement using an STM32 NUCLEO-F446RE, ESP32 wireless bridge, OLED display, and optional sensor-based event detection."

This wording is realistic, technically strong, and appropriate for a point-of-care prototype.
