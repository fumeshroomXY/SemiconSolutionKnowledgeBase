# Motor
A motor is an electrical device that converts electrical energy into **mechanical motion**.

Examples:
- Electric vehicle traction motors
- Factory conveyor motors
- Robot arm motors
- Air conditioner compressor motors
- Washing machine drum motors
- Fan motors

The microcontroller controls:
- Speed(how fast it spins, controlled by AC frequency)
- Direction
- Torque(how hard it twists, controlled by AC current)
- Position

## DC Motor
Can often run directly from DC power.

## AC Motor
Requires AC power.

Examples:
- EV traction motors
- Air conditioners
- Industrial robots

# Invertor
An inverter is a power electronics circuit that converts **DC power into controlled AC power**.

A typical setup looks like:
```
400V DC Power
    ↓
Inverter <- 3.3V PWM(Pulse Width Modulation) signals <- MCU
    ↓
3-Phase AC Motor
```

## DC vs AC
### DC(Direct Current)
Voltage stays in one direction.

Examples:
- Battery (EV battery, laptop battery)
- Solar panel output

### AC (Alternating Current)
Voltage changes magnitude, direction and frequency periodically.

# Why Are Special MCUs Needed?
Motor control applications require:
- Fast ADC sampling
- Precise PWM generation
- Real-time control loops
- Fault protection
- Encoder interfaces

Example control loop:
```
Current Sensor
↓
ADC
↓
RX72T MCU
↓
PWM Signals
↓
Inverter
↓
Motor
↓
Sensor
↓ (analog signals)
ADC
```

## Why ADC is needed
Because the MCU has to **measure what's happening in the real world** and use that information to control the motor.

- Measuring Motor Current
- Protecting the Motor
- Speed Control
- Motor Position

# PWM(Pulse Width Modulation)
A technique where the MCU rapidly turns a signal ON and OFF to changes the **average power** delivered to a device.

## Duty Cycle

Duty Cycle = ON Time / Total Time

Suppose the PWM output is 5V. 

#### 20% Duty Cycle
Average voltage: 5V × 20% = 1V
#### 80% Duty Cycle
Average voltage: 5V × 80% = 4V

The actual voltage is still switching between 0V and 5V, but many devices **behave as if they are receiving the average value**.

For a DC motor:
- 20% duty cycle → slow speed
- 50% duty cycle → medium speed
- 100% duty cycle → full speed

### Analogy

Imagine a light switch:
- ON all the time → full brightness
- OFF all the time → dark
- Rapidly ON/OFF → appears dimmer

## PWM and Inverters

In AC motor control:
The MCU generates precisely timed PWM signals.

The inverter's MOSFETs/IGBTs switch according to those PWM signals and create a waveform that **approximates a sine wave(AC)**.


## Why PWM
PWM lets the MCU control:

- Motor speed
- Motor torque
- LED brightness
- Power supplies
- Inverters

using simple digital outputs.
