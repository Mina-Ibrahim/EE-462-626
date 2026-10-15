# Bill of Materials (BOM) for the Point-of-Care Prototype

## Recommended Core BOM

| Item | Qty | Purpose | Estimated Price | DigiKey | Mouser | Amazon |
|---|---:|---|---:|---|---|---|
| STM32 NUCLEO-F446RE | 1 | Main embedded controller | $15–$25 | https://www.digikey.com/en/products/filter/development-boards-kits-programmers/277?keywords=NUCLEO-F446RE | https://www.mouser.com/c/?q=NUCLEO-F446RE | https://www.amazon.com/s?k=STM32+NUCLEO+F446RE |
| ESP32 Development Board | 1 | Wireless communication bridge | $8–$15 | https://www.digikey.com/en/products/filter/development-boards-kits-programmers/277?keywords=ESP32%20devkit | https://www.mouser.com/c/?q=ESP32+devkit | https://www.amazon.com/s?k=ESP32+DevKit |
| SSD1306 OLED 0.96" | 1 | Patient display | $5–$10 | https://www.digikey.com/en/products/filter/display-modules/1210?keywords=ssd1306 | https://www.mouser.com/c/?q=SSD1306+OLED | https://www.amazon.com/s?k=SSD1306+OLED |
| Tactile Push Buttons | 4 | UI navigation and selection | $2–$6 | https://www.digikey.com/en/products/filter/switches/139?keywords=push+button+switch | https://www.mouser.com/c/?q=push+button+switch | https://www.amazon.com/s?k=push+button+switch |
| Emergency Button | 1 | Immediate alert trigger | $2–$6 | https://www.digikey.com/en/products/filter/switches/139?keywords=emergency+button | https://www.mouser.com/c/?q=emergency+button+switch | https://www.amazon.com/s?k=emergency+button |
| Buzzer | 1 | Audible alert | $1–$4 | https://www.digikey.com/en/products/filter/audio-devices/170?keywords=buzzer | https://www.mouser.com/c/?q=buzzer | https://www.amazon.com/s?k=electronic+buzzer |
| Breadboard | 1 | Prototyping | $5–$12 | https://www.digikey.com/en/products/filter/prototyping-products/235?keywords=breadboard | https://www.mouser.com/c/?q=breadboard | https://www.amazon.com/s?k=breadboard |
| Jumper Wires | 1 set | Connections | $4–$8 | https://www.digikey.com/en/products/filter/wire-harnesses/484?keywords=jumper+wire+male+female | https://www.mouser.com/c/?q=jumper+wire | https://www.amazon.com/s?k=jumper+wires+male+female |
| 10k Resistors | 10 | Pull-ups / current limiting | $2–$5 | https://www.digikey.com/en/products/filter/resistors/54?keywords=10k+resistor | https://www.mouser.com/c/?q=10k+resistor | https://www.amazon.com/s?k=10k+resistor+pack |
| USB Cables | 1–2 | Programming / power | $4–$10 | https://www.digikey.com/en/products/filter/cables-wires/158?keywords=usb+micro+cable | https://www.mouser.com/c/?q=USB+micro+cable | https://www.amazon.com/s?k=USB+micro+cable |

### Core Total Estimate
- $48–$101 without sensors
- $60–$130 with extra prototyping accessories

## Recommended Sensor Add-ons

| Item | Qty | Purpose | Estimated Price | DigiKey | Mouser | Amazon |
|---|---:|---|---:|---|---|---|
| MPU6050 Accelerometer/Gyroscope | 1 | Fall detection / impact detection | $5–$12 | https://www.digikey.com/en/products/filter/sensors-transducers/196?keywords=mpu6050 | https://www.mouser.com/c/?q=MPU6050 | https://www.amazon.com/s?k=MPU6050+accelerometer |
| TMP117 Temperature Sensor | 1 | Fever / abnormal temp detection | $5–$10 | https://www.digikey.com/en/products/filter/sensors-transducers/196?keywords=TMP117 | https://www.mouser.com/c/?q=TMP117 | https://www.amazon.com/s?k=TMP117+temperature+sensor |
| LM35 Temperature Sensor | 1 | Lower-cost temperature option | $2–$6 | https://www.digikey.com/en/products/filter/sensors-transducers/196?keywords=LM35 | https://www.mouser.com/c/?q=LM35 | https://www.amazon.com/s?k=LM35+temperature+sensor |
| MAX30102 Pulse Sensor | 1 | Optional pulse monitoring | $8–$15 | https://www.digikey.com/en/products/filter/sensors-transducers/196?keywords=MAX30102 | https://www.mouser.com/c/?q=MAX30102 | https://www.amazon.com/s?k=MAX30102+sensor |
| DS3231 RTC Module | 1 | Time stamping of events | $5–$12 | https://www.digikey.com/en/products/filter/clock-timing-real-time-clocks/274?keywords=DS3231 | https://www.mouser.com/c/?q=DS3231 | https://www.amazon.com/s?k=DS3231+RTC+module |

### Sensor Add-on Total Estimate
- Minimal sensor package: $10–$25
- Strong sensor package: $25–$55

## Suggested Practical Final Build

Best realistic version for this project:
- STM32 NUCLEO-F446RE
- ESP32 DevKit
- SSD1306 OLED
- 4 buttons
- emergency button
- buzzer
- MPU6050
- TMP117 or LM35
- breadboard + wires
- 10k resistors

### Estimated Total for This Version
- $65–$150 depending on sensor choice and shipping

This is a good balance between capability, reliability, and project manageability.

## Notes
- DigiKey and Mouser are preferred for consistent electronic components.
- Amazon is useful for convenience and fast shipping but should be checked for exact module compatibility.
- The exact board chosen should match the project’s UART and I2C needs.
