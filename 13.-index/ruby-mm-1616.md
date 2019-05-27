# Ruby-MM-1616

### Overview

The RMM-1616A/AP is a family of PC/104 and PC/104-Plus I/O modules featuring 4, 8 or 16 16-bit analog voltage and current outputs, and 48 digital I/O lines. A 50-pin connector provides access to the 16 analog outputs, and another 50-pin connector provides access to the 48 digital I/O lines. The board operates over the extended temperature range of -40oC to +85oC

### Board Initialization

To use the Ruby-MM-1616 board in an appllication using the UD, the dscInitBoard function should use the board macro DSC\_RMM1616. This is shown in the example below.

```c
dscInitBoard(DSC_RMM1616, &dsccb, &board );
```

### Analog Input

Not supported by this board.

### Analog Output

|  |  |
| :--- | :--- |
| Max Output Channels: | 16 |
| D/A Resolution: | 16 bits \(1/65536 of full-scale\) |
| Data Range: | 0 to 65535 |
| Output Ranges \(Bipolar\): | ±10V, ±5V \(per each bank of 8 channels via jumper\) |
| Output Ranges \(Unipolar\): | 0-10V, 0-5V \(per each bank of 8 channels via jumper\) |

### Digital I/O

|  |  |
| :--- | :--- |
| Max Ports: | 6 bi-directional, programmable in 8-bit groups, TTL-compatible Digital I/O ports on Ruby-MM-1616 require direction to be set with DscDIOSetConfig\(\) before use. All DIO lines power-up in input mode and have readback capability. All DIO lines have User configurable pull-up resistors. |

### Ruby-MM-1616 Universal Driver Functions

* dscCancelOpType\(\) 
* dscCounterConfig\(\) 
* dscCounterFunction\(\) 
* dscCounterRate\(\) 
* dscCounterRead\(\) 
* dscDAConvert\(\) 
* dscDAConvertScan\(\) 
* dscDASetSettings\(\) 
* dscDASetSim\(\) 
* dscDIOInputBit\(\) 
* dscDIOInputByte\(\) 
* dscDIOOutputBit\(\) 
* dscDIOOutputByte\(\) 
* dscDIOSetConfig\(\) 
* dscLEDTest\(\) 
* dscPWMClear\(\) 
* dscPWMStart\(\) 
* dscSetPage\(\) 
* dscUserInt\(\) 
* dscWGBufferLoad\(\) 
* dscWGCommand\(\) 
* dscWGConfigSet\(\)

