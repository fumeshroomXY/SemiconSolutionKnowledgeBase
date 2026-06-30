# RX Driver Package
A software package for using **basic functions** such as initializing MCUs, programming flash memory, timer control, UART communications, and A/D conversion, 
and **application functions** such as USB and Ethernet transfer and control.

<img src = "/images/FIT.jpg" width = 80%>

<img src = "/images/RX-Driver-Package-structure.jpg" width = 100%>

# FIT
FIT consists of a Board Support Package (BSP), peripheral function modules, and middleware modules.

<img src = "/images/FITmodule.jpg" width = 80%>


#### BSP
- Module that performs **initial MCU settings, clock settings, board settings**, and so on

#### Peripheral Function Modules
- Drivers that control the peripheral functions of a RX microcontroller

#### Middleware Modules
- Middleware function such as TCP/IP and file system


# Advantages of FIT
## Embed Peripheral Function Modules With Ease
Peripheral function modules and middleware modules that support FIT operate in a common MCU basic setting (BSP).
<img src = "/images/UnifiedInitialSetting.jpg" width = 80%>


## Migrate Between RX Microcontrollers With Ease
Once FIT is supported, the APIs of peripheral driver modules and middleware modules have common specifications. The MCU can be switched easily to another MCU.
<img src = "/images/SwitchtoAnotherMCU.jpg" width = 80%>
