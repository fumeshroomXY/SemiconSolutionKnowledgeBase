# GLCDC = Graphics LCD Controller
It helps the MCU drive a display without burdening the CPU.
```
RX72N
↓
GLCDC
↓
LCD Panel
```
Without a GLCDC:
- CPU must constantly draw pixels
- Higher CPU load

With a GLCDC:
- Hardware handles screen refresh
- CPU can focus on application logic

Typical applications:

- Touchscreen HMIs
- Industrial panels
- Medical devices
- Smart appliances

Example:
```
+----------------+
| Temperature    |
|      25°C      |
| [Start] [Stop] |
+----------------+
```


# Crypto Engine
Instead of the CPU doing all calculations in software:
```
CPU
↓
Crypto Engine
↓
Encrypted Data
```
The hardware performs tasks such as:
- AES encryption
- SHA hashing
- Random number generation
- Secure key storage
- TLS/HTTPS acceleration

### Examples:
#### Secure Firmware Updates
```
Download firmware
↓
Crypto Engine verifies signature
↓
Install only trusted firmware
```
#### Secure Network Communication
```
RX72N
↓
TLS Encryption
↓
Cloud Server
```
The Crypto Engine makes encryption faster and more secure.

# EtherCAT(Ethernet for Control Automation Technology)
A special industrial networking protocol optimized for **real-time control** and used in **factory automation and motion control**.

## Why not use normal Ethernet?

Imagine a robot with:
- 8 servo motors
- Sensors
- Safety devices

The controller needs to communicate with all of them every millisecond or less.

Normal Ethernet is great for:

- Browsing websites
- Sending files
- Streaming video

But timing is not guaranteed:
```
Packet A: 1 ms
Packet B: 3 ms
Packet C: 8 ms
```
For robot control, that variability is a problem.

Consider a robot arm.
```
Joint 1 Motor
Joint 2 Motor
Joint 3 Motor
Joint 4 Motor
```
All motors must move together.

If one motor receives commands late:
```
Motor 1: 1.000 ms
Motor 2: 1.001 ms
Motor 3: 1.050 ms ← too late
```
the motion becomes inaccurate.


## What EtherCAT does
EtherCAT is designed so that a controller can talk to many devices with **extremely predictable timing**.

Example:
```
PLC / Controller
│
▼
Servo #1
│
▼
Servo #2
│
▼
Servo #3
│
▼
I/O Module
```
All devices are connected in a chain.

The EtherCAT frame passes through each device, which reads/writes its data "on the fly."
```
Controller → Device1 → Device2 → Device3
```
This makes communication very fast and gives synchronized timing:
```
Motor 1: 1.000 ms
Motor 2: 1.000 ms
Motor 3: 1.000 ms
Motor 4: 1.000 ms
```

# Wi-SUN FAN
A wireless networking technology designed for **large-scale IoT and utility networks**.

- **Wi-SUN** = Wireless Smart Utility Network
- **FAN** = Field Area Network

#### Wi‑Fi
```
Router
├─ Laptop
├─ Phone
└─ Tablet
```
Good for:
- Homes
- Offices
- High data rates

#### Wi-SUN FAN
```
Smart Meter #1
│
Smart Meter #2
│
Street Light
│
Sensor
│
Gateway
```
Good for:
- Smart cities
- Utility meters
- Outdoor sensors
- Large industrial sites

## Key Feature: Mesh Networking
Unlike Wi‑Fi, devices can relay messages for each other.
```
Sensor A → Sensor B → Sensor C → Gateway
```
Even if Sensor A cannot reach the gateway directly, the network still works.

This is called a **mesh network**.

### Why is it useful?
Imagine a city with:

- 10,000 electric meters
- 5,000 water meters
- 2,000 street lights

Running Ethernet cables everywhere would be expensive.

Wi‑SUN allows all these devices to communicate wirelessly.
```
Electric Meter
↓
Wi-SUN
↓
Utility Company
```

# BT5 LE(Bluetooth 5 Low Energy, BLE 5)
BLE is a version of Bluetooth designed for:
- Low power consumption
- Battery-powered devices
- IoT products
- Sensors and wearables

Typical Applications
- Fitness Tracker
- Smart Lock
- Industrial Sensor

# DSAD(Delta-Sigma A/D Converter ΔΣ ADC)
## Why use a DSAD instead of a normal ADC?
A normal ADC (SAR ADC) is typically:
- Fast
- Medium precision
```
12-bit ADC
0 ~ 4095 counts
```
A DSAD is:
- Slower
- Much higher precision
```
24-bit DSAD
0 ~ 16,777,215 counts
```
This allows the MCU to measure **very small signal changes**.

Best for:
- Digital weighing scales
- Precision sensors
- Laboratory instruments

## HS DSAD
HS = High Speed

It keeps the high accuracy of a Delta-Sigma ADC while providing faster measurements.


# TFU(Trigonometrical Function Unit)
A special hardware accelerator can perform trigonometric calculations such as:
- Sine (sin)
- Cosine (cos)
- Arctangent (atan)
- Vector calculations

## Without TFU
The CPU must calculate:
```
sin(angle)
cos(angle)
atan(y/x)
```
using software libraries.
- Takes CPU cycles
- Increases control-loop execution time

## With TFU
The MCU has dedicated hardware:
```
CPU
↓
TFU
↓
sin/cos result
```
The result comes much faster, leaving more CPU time for:
- Motor-control algorithms
- Communication
- Safety functions

#### Example: Controlling a Motor
```
Current Sensors
      ↓
ADC
      ↓
RX14T
      ↓
TFU computes:
  sin(θ)
  cos(θ)
      ↓
PWM
      ↓
Inverter
      ↓
Motor
```
The TFU helps the MCU determine the correct PWM signals to generate the desired torque and speed.

# Touch
"Touch" means the MCU has **capacitive touch** sensing hardware built into it.
## Capacitive Touch
It's the same technology used in:
- Smartphone touchscreens
- Touch buttons on appliances
- Microwave control panels
- Washing machine control panels

you just touch a surface:
```
Finger
↓
Touch panel
↓
MCU detects touch
```

