# GPIO-MM-11

### Overview

GPIO-MM-11 and GPIO-MM-12 boards provide 48 lines of DIO and 2 9513 based 16 bit counter timers.

### Board Initialization

To use the GPIO-MM-11/12 board in an appllication using the UD, the application needs to perform a dscInitBoard on the hardware feature that is desired in the application.

The GPIO-MM-11 has two separate base address ranges for the two distinct hardware features. The DIO section of the hardware is controlled by a base address which is different from the base address for the register set to control the 9513 based counter timer circuitry.

Thus the application needs to perform a dscInitBoard twice if both the DIO and the counter timer functionality is desired.

This is shown in an example below. To use DIO functionality, use

```c
dscInitBoard( DSC_GPIO11_DIO , &dsccb, &board );
```

To use the 9513 counter/timer functionality, use

```c
dscInitBoard( DSC_GPIO11_9513, &dsccb1, &board1 );
```

### Digital I/O

|  |  |
| :--- | :--- |
| Max Ports: | 6 8-bit bi-directional ports with programmable direction bit by bit and inverting logic Digital I/O lines on GPIO-MM-11 do not require configuration. Writing a 0 to any bit drives the pin high and also enables it as an input. Writing a 1 to a bit drives the pin low and forces it to an output. A high input will read back as a 0, and a low input will readback as a 1. |
| Interrupts: | 2 with jumper-selected IRQ levels |
| Fixed Ports: | 8 fixed input ports, 8 fixed output ports |
| Counter/Timers: | 2 9513 16-bit counter/timers with programmable sources and cascading |

Refer to the GPIO-MM-11 user manual for detailed information on the counter and interrupt circuit features and configuration. Also refer to the user interrupt function descriptions in this manual for information on how to configure the counters and interrupts for your application.

### GPIO-MM-11 Universal Driver Functions

* dsc9513CounterControl\(\) 
* dsc9513MeasureFrequency\(\) 
* dsc9513MeasurePeriod\(\) 
* dsc9513PulseWidthModulation\(\) 
* dsc9513ReadHoldRegister\(\) 
* dsc9513Reset\(\) 
* dsc9513SetCMR\(\) 
* dsc9513SetHoldRegister\(\) 
* dsc9513SetLoadRegister\(\) 
* dsc9513SetMMR\(\) 
* dsc9513SingleCounterControl\(\) 
* dsc9513SpecialCounterFunction\(\) 
* dscCancelOp\(\) 
* dscDIOClearBit\(\) 
* dscDIOInputBit\(\) 
* dscDIOInputByte\(\) 
* dscDIOOutputBit\(\) 
* dscDIOOutputByte\(\) 
* dscDIOSetBit\(\) 
* dscGetEEPROM\(\) 
* dscGetStatus\(\) 
* dscInterruptControl\(\) 
* dscSetEEPROM\(\) 
* dscSetUserInterruptFunction\(\) 
* dscUserInt\(\)



