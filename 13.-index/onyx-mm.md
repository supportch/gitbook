# Onyx-MM

### Board Initialization

To use the Onyx-MM board in an appllication using the UD, the dscInitBoard function should use the board macro DSC\_OMM. This is shown in the example below.

```c
dscInitBoard( DSC_OMM , &dsccb, &board );
```

### Digital I/O

|  |  |
| :--- | :--- |
| Ports: | 6 8-bit bidirectional ports \(2 82C55 chips\) Digital I/O ports on Onyx-MM require direction to be set with dscDIOSetConfig before use. One configuration byte is required for each 82C55 chip. All DIO lines power-up in input mode and have readback capability. All DIO lines have 10K Ohm pull-up resistors. |
| Interrupts: | 3 interrupts with programmable sources and jumper-configured IRQ levels |
| Counter/Timers: | 3 16-bit counter/timers with programmable sources and cascading |

Refer to the Onyx-MM user manual for detailed information on the counter and interrupt circuit features and configuration. Also refer to the user interrupt function descriptions in this manual for information on how to configure the counters and interrupts for your application.

### Onyx-MM Universal Driver Functions

* dscClearUserInterruptFunction\(\) 
* dscCounterDirectSet\(\) 
* dscCounterRead\(\) 
* dscCounterSetRate\(\) 
* dscCounterSetRateSingle\(\) 
* dscDIOClearBit\(\) 
* dscDIOInputBit\(\) 
* dscDIOInputByte\(\) 
* dscDIOOutputBit\(\) 
* dscDIOOutputByte\(\) 
* dscDIOSetBit\(\) 
* dscDIOSetConfig\(\) 
* dscSetUserInterruptFunction\(\) 
* dscUserInt\(\)

