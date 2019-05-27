# Onyx-MM-DIO

### Board Initialization

To use the Onyx-MM-DIO board in an appllication using the UD, the dscInitBoard function should use the board macro DSC\_OMMDIO. This is shown in the example below.

```c
dscInitBoard( DSC_OMMDIO , &dsccb, &board );
```

### Digital I/O

|  |  |
| :--- | :--- |
| Ports: | 6 8-bit bidirectional ports \(2 82C55 chips\) Digital I/O ports on Onyx-MM-DIO require direction to be set with dscDIOSetConfig\(\) before use. One configuration byte is required for each 82C55 chip. All DIO lines power-up in input mode and have readback capability. All DIO lines have 10K Ohm pull-up resistors. Interrupts Not supported on this board. |

### Onyx-MM-DIO Universal Driver Functions

* dscDIOClearBit\(\) 
* dscDIOInputBit\(\)
* dscDIOInputByte\(\) 
* dscDIOOutputBit\(\) 
* dscDIOOutputByte\(\) 
* dscDIOSetBit\(\) 
* dscDIOSetConfig\(\)

