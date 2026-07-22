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
- Speed(how fast it spins)
- Direction
- Torque(how hard it twists)
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
```

