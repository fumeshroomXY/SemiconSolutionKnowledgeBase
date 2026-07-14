# Renesas MCU & MPU
| Family                             | Type         | CPU Core         |CPU Main P       | Main Use Cases                                                           |
| ---------------------------------- | ------------ | -----------------|----------       | ------------------------------------------------------------------------ |
| **RA Arm Cortex‑M MCUs**           | MCU          | Arm Cortex‑M     | 32MHz ~ 1GHz    | General embedded systems, IoT, industrial control, consumer electronics  |
| **RZ 32 & 64‑Bit MPUs**            | MPU          | Arm Cortex‑A     | 400MHz ~ 1.8GHz | **Linux-based** systems, HMI, gateways, AI edge devices                      |
| **RL78 Low‑Power 8 & 16‑Bit MCUs** | MCU          | Renesas RL78     | 16MHz ~ 32MHz   | Ultra-low-power sensors, meters, appliances, battery devices             |
| **RX 32‑Bit MCUs**                 | MCU          | Renesas RX core  | 32MHz ~ 240MHz  | Higher-performance embedded control without needing Linux                |
| **RH850 Automotive MCUs**          | MCU          | RH850            | 240MHz ~ 400MHz | Automotive ECUs, ADAS, body control, powertrain, functional safety       |


## RA
### Example products
- Smart thermostats
- Smart locks
- Industrial sensors
- EV charging stations
- Building automation controllers
- Medical monitoring devices
- Smart meters


### Example project
#### Smart Energy Meter
- Reads voltage/current sensors
- Stores data in flash memory
- Communicates through Wi-Fi, BLE, or MQTT
- Runs FreeRTOS

## RX
### Example products
- Servo motor controllers
- Factory automation equipment
- Inverters
- Robotics
- High-end industrial networking devices
- Digital power supplies

### Example project

#### Industrial Motor Drive
- Fast ADC sampling
- Real-time current control loops
- PWM generation
- Safety monitoring

### Why choose RX over RA?
- Very efficient real-time processing
- Strong motor-control ecosystem
- Legacy industrial customers often already use RX

## Simple Rule of Thumb
- RA → "I need a modern microcontroller."
- RX → "I need extremely fast real-time control."
- RZ → "I need Linux, graphics, or AI."
- RH850 → "I am building something that goes into a car."
- RL78 → "I need a battery-powered or very cost-sensitive controller."


