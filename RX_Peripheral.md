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


# 
