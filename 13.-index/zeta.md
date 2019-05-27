# Zeta

### Overview

The Zeta COM Express SBC family of ultra-small embedded computer boards combines a COM Express Mini CPU module mounted on a same-size carrier board to create a complete embedded PC. Zeta integrates onboard memory, one PCIe/MiniCard socket, dual Gigabit Ethernet, and optional data acquisition circuit with analog and digital I/O.

The SBC provides an optional data acquisition circuit containing analog input, analog output, and additional digital I/O features. This circuit is controlled by an FPGA interfaced to the processor via LPC.

### Board Initialization

To use the Zeta board in an appllication using the UD, the dscInitBoard function should use the board macro DSC\_ZETA. This is shown in the example below.

The base address should be 0x200 and the default IRQ to use is IRQ 5.

```c
dscInitBoard(DSC_ZETA, &dsccb, &board );
```

### Analog Input

|  |  |
| :--- | :--- |
| Max Input Channels: | 16 \(single-ended\) or 8 \(differential\) |
| A/D Resolution: | 16 bits \(1/65536 of full-scale\) |
| Data range: | -32768 to +32767 for all voltrage ranges. |
| Input Ranges \(Bipolar\): | ±10V, ±5V |
| Input Ranges \(Unipolar\): | 0-10V, 0-5V. |
| Supported Conversion Triggers: | Software, External digital signal, programmable clock. |
| Maximum Conversion Rate \(Software Command\): | approx. 100,000 samples per second, depending on code and operating system. |
| FIFO: | 2048 samples with Programmable interrupt threshold. |

### Analog Output

|  |  |
| :--- | :--- |
| Max Output Channels: | 4 |
| D/A Resolution: | 16 bits \(1/65536 of full scale\) |
| Data range: | 0 to 65535 for all voltage ranges |
| Bipolar Output Ranges: | ±10V, ±5V. |
| Unipolar Output Ranges: | 0-10V, 0-5V |

### Digital I/O

|  |  |
| :--- | :--- |
| Max Ports: | 3, bi-directional, 27 lines organized as 2 8-bit ports and 11 1-bit portson Prometheus require direction to be set with DscDIOSetConfig before use. All DIO lines power-up in input mode and have readback capability. All DIO lines have User-selectable 10K pull resistors that can be configured for all pull-up or all pull-down with a jumper. |

### Zeta Universal Driver Functions

* dscADIntCancel\(\) 
* dscADIntStatus\(\) 
* dscADSample\(\) 
* dscADSampleInt \(\) 
* dscADScan\(\) 
* dscADSetSettings\(\) 
* dscADSetTiming\(\) 
* dscCancelOpType\(\) 
* dscCounterConfig\(\) 
* dscCounterDirectSet\(\) 
* dscCounterRate\(\) 
* dscCounterRead\(\) 
* dscCounterReset\(\) 
* dscDAConvert\(\) 
* dscDAConvertScan\(\) 
* dscDASetSettings\(\) 
* dscDIOInputBit\(\) 
* dscDIOInputByte\(\) 
* dscDIOIntCancel\(\) 
* dscDIOOutputBit\(\) 
* dscDIOOutputByte\(\) 
* dscDIOOutputInt\(\) 
* dscDIOSetConfig\(\) 
* dscLEDTest\(\) 
* dscPauseOp\(\) 
* dscPWMClear\(\) 
* dscPWMStart\(\) 
* dscResumeOp\(\) 
* dscUserInt\(\) 
* dscUserIntRun\(\) 
* dscWGBufferLoad\(\) 
* dscWGCommand\(\) 
* dscWGConfigSet\(\)

