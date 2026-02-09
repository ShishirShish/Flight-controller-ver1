🛩️ Flight Controller – Custom STM32-Based Design
This repository contains the complete hardware design of a custom STM32-based flight controller, intended for multirotor UAVs and embedded control applications.
The project focuses on robust power design, precise sensor integration, and clean signal routing, suitable for research, academic, and prototyping use.

📌 Features Overview
Microcontroller: STM32F446RETx
Sensors:
6-axis IMU (Accelerometer + Gyroscope)
Barometric pressure sensor
Clocking: External 8 MHz crystal
Power:
USB-powered input
Onboard 3.3 V LDO regulation
Proper filtering and decoupling

Interfaces:

USB (device)
I²C
SPI
UART
CAN

SWD (programming & debugging)

Motor Control:
PWM outputs for ESCs

Timer-based channels

Designed in: KiCad 9.0.6

🧠 Hardware Architecture
1️⃣ Main Controller

STM32F446RE

External 8 MHz crystal with 20 pF load capacitors

SWD interface for debugging and flashing

Proper VCAP, VDDA, and decoupling network

2️⃣ Sensors
IMU (Accelerometer + Gyro)

I²C interface

Dedicated local decoupling capacitors

Pull-up resistors on SDA/SCL

Interrupt pins routed to MCU

Barometer

I²C interface

Configurable I²C address

Separate power filtering

3️⃣ Power Supply

USB 5 V input

Fuse and reverse protection

Low-noise 3.3 V LDO regulator

Power indication LED

Proper bulk and ceramic capacitors

4️⃣ ESC & PWM Outputs

Timer-based PWM outputs

Dedicated headers for ESC signal + power

Designed to support multirotor configurations

5️⃣ Communication Interfaces

USB (DFU / CDC capable)

Multiple UARTs

SPI (sensor expansion)

CAN bus

GPIO expansion headers

🔌 Pin Highlights
Interface	Purpose
TIM2 / TIM3	PWM outputs for ESCs
I2C1 / I2C3	IMU & Barometer
USB FS	Programming / telemetry
SWD	Debugging
CAN	External communication
ADC	Voltage / analog sensing
🧪 Design Considerations

Extensive decoupling and filtering

Ferrite bead isolation for analog supply

RC low-pass filters for ADC inputs

Separate sensor and digital domains

Designed with noise-sensitive IMU placement in mind
