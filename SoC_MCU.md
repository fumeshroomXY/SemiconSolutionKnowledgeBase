# SoC VS. MCU

**SoC** = very fast but many things are happening simultaneously.

**MCU** = less powerful but behaves more predictably.

Imagine a control task:
```markdown
Every 100 μs:
    Read sensor
    Calculate
    Update motor PWM
```

The MCU may be doing almost nothing else:
```markdown
Interrupt occurs
↓
Run control algorithm
↓
Update PWM
↓
Done (Maybe always 40 μs every cycle)
```

SoC at the same moment:
```markdown
Linux scheduler
Network stack
Camera driver
Graphics rendering
File system
Background services
Control task

Your task may have to wait:
Cycle 1: 20 μs
Cycle 2: 70 μs
Cycle 3: 35 μs
Cycle 4: 150 μs
```
Average performance is high.

Worst-case latency is **harder to guarantee**.


## Throughput vs Latency
**MCU** is optimized for **latency**:
```
Event occurs
↓
Respond immediately
```

**SoC** is optimized for **throughput**:
```
Process huge amounts of work per second
```


## Automotive Example
### Airbag Deployment
- Requirement: Deploy within 2 ms
- Engineers don't care if the average response is: 0.1 ms
- What matters is: **Worst case < 2 ms**

### Camera Object Detection
- Requirement:
```
Process 8 cameras
Run neural networks
Render displays
```
- **Average performance** matters much more than microsecond-level predictability.

## The Real Difference
| Platform | Average Time | Worst Case |
| -------- | ------------ | ---------- |
| MCU      | 40 μs        | 42 μs      |
| SoC      | 10 μs        | 500 μs     |

Notice that the SoC is **faster on average**, but the MCU is **much more predictable**.
That's why:
- **RH850** is chosen for brakes, steering, motor control, airbags.
- **R-Car** is chosen for navigation, cameras, displays, AI, infotainment.


