# Opal-MM

### Board Initialization

To use the Opal-MM board in an appllication using the UD, the dscInitBoard function should use the board macro DSC\_OPMM. This is shown in the example below.

```c
dscInitBoard( DSC_OPMM , &dsccb, &board );
```

### Digital I/O

|  |  |
| :--- | :--- |
| Interrupts | Not supported on this board. |
| Max Input Ports: | 8 lines \(1 byte or 8 bits\), optoisolated, inverting logic \(high input = 0, low input = 1\) |
| Max Output Ports: | 8 lines \(1 byte or 8 bits\), type SPDT \(form C\) relays A 1 in each bit turns that relay on, and a 0 turns it off. All relays power up in the off \(0\) position. The output ports do not have readback capability. |

The inputs and outputs are fixed direction and do not need configuration prior to use.

### Opal-MM Universal Driver Functions

* dscDIOClearBit\(\) 
* dscDIOInputBit\(\) 
* dscDIOInputByte\(\) 
* dscDIOOutputBit\(\) 
* dscDIOOutputByte\(\) 
* dscDIOSetBit\(\)

