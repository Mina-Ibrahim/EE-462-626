# Embedded Implementation Plan

## 1. Goal

Build a working prototype that demonstrates patient event reporting using an STM32 microcontroller, an ESP32 wireless bridge, and a simple caregiver interface.

## 2. Phase 1: Hardware Bring-Up

### Tasks
- Connect the STM32 NUCLEO-F446RE to a computer
- Confirm toolchain works and the board programs successfully
- Test LED blink to verify the build environment
- Connect OLED display over I2C
- Verify the OLED initializes and displays text
- Connect buttons to GPIO inputs
- Add buzzer output
- Add emergency button input

### Deliverable
- Functional board with display and button input

## 3. Phase 2: Menu and State Machine

### Tasks
- Define UI states such as:
  - MAIN_MENU
  - EVENT_SELECT
  - CONFIRM_EVENT
  - SEND_MESSAGE
  - WAIT_ACK
  - DISPLAY_RESPONSE
  - EMERGENCY_ALERT
- Implement navigation with Up, Down, Select, and Back buttons
- Add emergency override path
- Add simple event selection logic

### Deliverable
- A working patient menu system

## 4. Phase 3: Event Logic

### Events to implement first
- Pain
- Breathing issue
- Dizziness
- Need assistance
- Medication reminder
- Emergency button

### Optional later events
- Fall detection using MPU6050
- Fever using temperature sensor
- Long inactivity warning

### Deliverable
- Patient can select and confirm an event

## 5. Phase 4: Sensor Integration

### Tasks
- Add MPU6050 accelerometer and detect impact/fall-like motion
- Add temperature sensor and evaluate threshold logic
- Add filtering to reduce false positives

### Deliverable
- Event data can include sensor-based readings

## 6. Phase 5: UART and ESP32 Communication

### Tasks
- Connect STM32 UART to ESP32
- Confirm serial communication is stable
- Send message packet from STM32 to ESP32
- Receive acknowledgement and response from ESP32 or laptop interface

### Deliverable
- Reliable message transfer between embedded modules

## 7. Phase 6: Wireless and Caregiver Side

### Tasks
- Create a simple laptop interface
- Receive packet from ESP32 over Wi-Fi or serial bridge
- Display event in a clear list or dashboard
- Allow caregiver to send acknowledgement or response

### Deliverable
- End-to-end communication from patient device to caregiver interface

## 8. Phase 7: Reliability and Robustness

### Tasks
- Add timeout for acknowledgement
- Retry logic
- Checksum validation
- Event priority handling
- Fail-safe state for communication errors

### Deliverable
- Reliable communication under expected failure conditions

## 9. Phase 8: Testing and Demonstration

### Test Cases
- Normal symptom report
- Emergency button press
- Fall detection trigger
- No acknowledgement received
- Corrupted packet handling
- Invalid button input

### Deliverable
- Demonstrated proof-of-concept working flow

## 10. Suggested MVP

The minimum strong implementation should include:
- OLED + buttons
- emergency button
- event selection
- UART to ESP32
- acknowledgement logic
- laptop caregiver interface
- one fall trigger or high-priority alert

This is the best realistic target for a successful project.

## 11. Default Implementation Priority

1. Buttons and menu system
2. OLED display
3. STM32 to ESP32 UART communication
4. Basic care event messages
5. Emergency event handling
6. Acknowledgement and timeout logic
7. MPU6050 fall detection
8. Temperature sensor
9. Final polish and demo

## 12. Final Recommendation

The strongest strategy is to implement the project in layers: first a reliable menu-driven UI, then UART communication, then event logic, and only then sensor enhancements. This keeps the project achievable while still making the final result impressive.
