# Point-of-Care Patient Communication and Emergency Alert Prototype

## Abstract

This project presents the design and development of a point-of-care communication prototype that allows a patient to report important health-related events to a caregiver using an embedded system. The proposed system uses an STM32 NUCLEO-F446RE as the primary microcontroller and an ESP32 as a wireless communication bridge. Patients interact with the device through a small OLED display and a set of physical buttons to report symptoms, request assistance, or trigger an emergency alert. The system formats the input into a structured message and transmits it to a doctor or caregiver interface for acknowledgement and response.

The prototype is intended to demonstrate practical embedded systems concepts including GPIO control, I2C communication, UART communication, button-driven menu systems, state-machine logic, wireless communication, packet formatting, and error handling. It is designed as a proof-of-concept point-of-care communication device rather than a clinical diagnostic system.

## 1. Introduction

Modern healthcare environments rely heavily on timely communication between patients and clinicians. Patients may need to request assistance, communicate pain or discomfort, report dizziness, indicate shortness of breath, or alert staff after a fall. In many cases, communication is delayed because patients must wait for a nurse or clinician to become available. This may create delays in monitoring and response.

The goal of this project is to develop a prototype embedded system that allows a patient to report structured events quickly and clearly. The system is intended to show how a low-cost embedded device can provide a simple communication interface between a patient and a caregiver. The design emphasizes communication reliability, event prioritization, and response acknowledgement rather than diagnosis.

## 2. Problem Statement

Patients often need to communicate important information to caregivers in real time, but conventional communication methods can be slow or difficult to manage in busy clinical settings. The problem is not simply a lack of communication devices, but a lack of a structured and reliable method to communicate meaningful events in a consistent format.

This project addresses the question: how can an embedded system be designed to allow a patient to report structured health events and emergency incidents to a caregiver in a clear, reliable, and efficient manner while also supporting acknowledgement and response?

## 3. Objectives

The main objective of the project is to create a functional point-of-care communication prototype that demonstrates reliable patient-to-caregiver communication and alert reporting.

The project objectives are as follows:

- Use the STM32 NUCLEO-F446RE as the main controller
- Develop a menu-based patient interface using buttons and an OLED display
- Enable the patient to report health-related events and requests for help
- Support event categories such as pain, dizziness, breathing difficulty, fall, assistance request, fever, and inactivity alerts
- Use optional sensors for motion and temperature measurement
- Create structured communication packets containing event metadata
- Transmit data from the STM32 to the ESP32 using UART
- Use the ESP32 to relay information over Wi-Fi to a caregiver or doctor interface
- Receive acknowledgement or responses from the caregiver device
- Display the response back to the patient on the OLED screen
- Implement timeout and retry logic for unreliable communication
- Demonstrate a practical embedded point-of-care prototype

## 4. System Overview

The proposed system is composed of the following modules:

### 4.1 Patient Input Interface
The patient interacts with the device through a set of buttons and an OLED display. A dedicated emergency button can also be included to trigger an urgent alert.

### 4.2 Embedded Control Unit
The STM32 microcontroller is responsible for reading inputs, updating the user interface, interpreting menu selections, and generating structured communication packets. It can also manage optional sensors and system state transitions.

### 4.3 Wireless Relay
The ESP32 acts as a communication bridge between the patient device and the caregiver interface. It receives packets from the STM32 over UART and sends them over Wi-Fi to a laptop or monitoring terminal.

### 4.4 Caregiver Interface
The caregiver interface is implemented on a laptop or desktop computer. It receives patient events, displays them in a clear format, and allows a nurse or clinician to acknowledge or respond to the event.

### 4.5 Patient Feedback
The device then displays the caregiver’s response or acknowledgement on the OLED screen so the patient knows the message was received.

## 5. Practical Event Types

The prototype will prioritize event types that are meaningful in a bedside care setting. The following patient events are considered relevant and practical for a prototype implementation:

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

These events can be categorized into routine, urgent, and emergency priority levels. A fall, breathing difficulty, or emergency activation should be assigned higher priority than a normal comfort check or medication reminder.

## 6. Hardware Architecture

The system uses the following hardware components:

- STM32 NUCLEO-F446RE as the main controller
- ESP32 development board for wireless communication
- SSD1306 OLED display for patient feedback
- Push buttons for menu navigation
- Emergency button for direct alert trigger
- Buzzer for system alerts
- MPU6050 accelerometer for fall detection
- Temperature sensor for fever monitoring
- Optional pulse sensor for additional monitoring
- Breadboard and jumper wires for prototyping

## 7. Software Architecture

The software design should follow a modular structure and use a finite state machine for menu and event handling. The primary software modules include:

- User interface module
- Event selection logic
- Sensor acquisition module
- Communication protocol module
- UART interface module
- Wi-Fi relay logic
- Acknowledgement and retry module
- Error detection and timeout handling

This software architecture makes the prototype easier to test and expand and supports future additions such as more sensors or additional event types.

## 8. Communication Protocol

A structured communication protocol should be used instead of plain text alone. The prototype should transmit information in a packet format that contains key metadata such as:

- Message ID
- Event Type
- Severity Level
- Patient or Room ID
- Timestamp
- Optional Sensor Value
- Checksum or validation byte

This improves communication reliability and allows the interface to distinguish between routine, urgent, and emergency messages.

## 9. Error Handling and Reliability

The system should include a basic acknowledgement and retry mechanism. When a message is sent, the caregiver interface should respond with an acknowledgement. If no acknowledgement is received within a set time window, the patient device should display a warning and allow the user to retry or escalate the alert. A checksum or CRC can also be used to detect corrupt or incomplete messages.

These measures are important because communication reliability is a core requirement in a point-of-care system.

## 10. Safety and Scope Boundaries

This project is intentionally designed as a prototype and does not aim to diagnose medical conditions or replace professional clinical monitoring equipment. It is intended to demonstrate how patient communication and alerting can be structured using embedded systems.

The prototype is therefore best described as a point-of-care communication and emergency alert proof of concept rather than a medical-grade device.

## 11. Expected Results

The project will be considered successful if the following can be demonstrated:

- The patient can navigate the menu and select an event
- The device displays a confirmation message on the OLED screen
- The event is transmitted through the STM32-to-ESP32 UART link
- The ESP32 sends the event to a caregiver interface
- The caregiver interface receives the message and acknowledges it
- The response is displayed back to the patient
- A fall, emergency, or high-priority event triggers an alert flow

## 12. Conclusion

This project combines embedded systems, wireless communication, sensor integration, and patient interaction into a meaningful point-of-care prototype. It is technically suitable for an academic project because it covers a wide range of practical topics while remaining manageable in scope. The design also has strong demonstrable value because it can clearly show a patient-triggered event being communicated to a caregiver and acknowledged in real time.

The project is therefore a strong proof-of-concept for embedded patient communication and emergency alert systems.
