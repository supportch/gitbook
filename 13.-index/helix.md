# Helix

### Overview

Helix SBCs use the Vortex86DX3 SoC from DMP Electronics. It is a 32-bit x86 architecture dual-core 1GHz microprocessor designed for ultra-low power consumption, combining both the North and South bridges with a rich set of integrated features including a 32KB write through 8-way L1 cache, 512KB write through/write back 4- way L2 cache, PCIe bus at 2.5 GHz, DDR3 controller, ISA, I2C, SPI, IPC \(includes Internal Peripheral Controllers with DMA and interrupt timer/counter\), Fast Ethernet, FIFO UART, USB2.0 Host, and an IDE/SATA controller. The SBC supports up to 2GB of DDR3 memory soldered on-board.

The SBC provides four serial ports: two with fixed RS-232 capability using SP211EHEA-L, and a second two having RS-232/422/485 capability using a SP336. The built-in UARTs from the VortexDX3 are used. In RS-232 mode, only the signals TX, RX, RTS, and CTS are provided. Protocol selection for serial ports 3-4 is controlled using GPIO pins from the SoC and is configurable via BIOS configuration screens as well as via application software. Jumpers are used to enable termination resistors \(121 Ohm\) for RS-422 and RS-485 protocols. Console redirection, using a serial port

### Board Initialization

To use the Helix board in an appllication using the UD, the dscInitBoard function should use the board macro DSC\_HELIX. This is shown in the example below.

```c
dscInitBoard(DSC_HELIX, &dsccb, &board );
```

### Analog Input

|  |  |
| :--- | :--- |
| Max Input Channels: | 16 \(single-ended\) or 8 \(differential\) |
| A/D Resolution: | 16 bits \(1/65536 of full-scale\) |
| Data range: | -32768 to +32767 for all voltage ranges |
| Input Ranges \(Bipolar\): | ±10V, ±5V |
| Input Ranges \(Unipolar\): | 0-10V, 0-5V. |
| Supported Conversion Triggers: | Software, External digital signal, programmable clock. |
| Maximum Conversion Rate \(Software Command\): | approx. 100,000 samples per second, depending on code and operating system |
| FIFO: | 2048 samples with Programmable interrupt threshold |

### Analog Output

|  |  |
| :--- | :--- |
| Max Output Channels: | 4 |
| D/A Resolution: | 16 bits \(1/65536 of full scale\) |
| Data range: | 0 to 65535 for all voltage ranges |
| Bipolar Output Ranges: | ±10V, ±5V. |
| Unipolar Output Ranges: | 0-5V, 0-2.5V. |

### Digital I/O

|  |  |
| :--- | :--- |
| Max Ports: | 3, bi-directional, 27 lines organized as 2 8-bit ports and 11 1-bit ports on Prometheus require direction to be set with DscDIOSetConfig\(\) before use. All DIO lines power-up in input mode and have readback capability. All DIO lines have User-selectable 10K pull resistors that can be configured for all pull-up or all pull-down with a jumper. |

### Helix Universal Driver Functions

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
* dscCounterFunction\(\) 
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

