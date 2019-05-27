# Diamond-MM-16RP-AT

### Overview

DMM-16RP-AT is a of PC/104 and PC/104-Plus I/O modules featuring analog and digital I/O modules. The module is ideal for add-on data acquisition I/O expansion in embedded and OEM applications. It offers 16 single ended or 8 differential 16-bit analog inputs with an aggregate sample rate of 100 KHz maximum, 512 sample A/D FIFO, four 12-bit analog outputs, and 16 digital I/O lines. The buffered digital I/O lines can be optionally configured as either pulse width modulators or counter/timers.

### Board Initialization

To use the Diamond-MM-16RP-AT board in an appllication using the UD, the dscInitBoard function should use the board macro DSC\_DMM16RPAT. This is shown in the example below.

```c
dscInitBoard(DSC_DMM16RPAT, &dsccb, &board );
```

### Analog Input

|  |  |
| :--- | :--- |
| Max Input Channels: | 16 \(single-ended\) or 8 \(differential\) |
| A/D Resolution: | 16 bits \(1/65536 of full-scale\) |
| Data range: | -32768 to +32767 for all voltrage ranges |
| Input Ranges \(Bipolar\): | ±10V, ±5V, ±2.5V, ±1.25V |
| Input Ranges \(Unipolar\): | 0-10V, 0-5V,0-2.5V |
| Supported Conversion Triggers: | Software, External digital signal, programmable clock. |
| Maximum Conversion Rate \(Software Command\): | approx. 100,000 samples per second, depending on code and operating system |
| FIFO: |  512 samples with Programmable interrupt threshold |

### Analog Output

|  |  |
| :--- | :--- |
| Max Output Channels: | 4 |
| D/A Resolution: | 12 bits \(1/4096 of full scale\) |
| Data range: | 0 to 4095 for all voltage ranges |
| Bipolar Output Ranges: | ±5V |
| Unipolar Output Ranges: | 0-5V, 0 – \(user-programmable\) |

### Digital I/O

|  |  |
| :--- | :--- |
| Max Ports: | 2, two 8-bit ports and Prometheus require direction to be set with DscDIOSetConfig\(\) before use. All DIO lines power-up in input mode and have readback capability. All DIO lines have User-selectable 10K pull resistors that can be configured for all pull-up or all pull-down with a jumper. |

### Diamond-MM-16-AT Universal Driver Functions

* dscADAutoCal\(\) 
* dscADCalVerify\(\)
* dscADIntStatus\(\) 
* dscADSample\(\) 
* dscADSampleInt \(\) 
* dscADScan\(\) 
* dscADScanInt\(\) 
* dscADSetChannel\(\) 
* dscADSetScan\(\) 
* dscADSetSettings\(\) 
* dscCancelOpType\(\) 
* dscCounterDirectSet\(\) 
* dscCounterRead\(\) 
* dscCounterSetRate\(\) 
* dscCounterSetRateSingle\(\) 
* dscDAAutoCal\(\) 
* dscDACalVerify\(\) 
* dscDAConvert\(\)
* dscDAConvertScan\(\) 
* dscDAConvertScanInt\(\) 
* dscDIOInputBit\(\) 
* dscDIOInputByte\(\) 
* dscDIOOutputBit\(\) 
* dscDIOOutputByte\(\) 
* dscDIOSetConfig\(\) 
* dscFifoStatus\(\) 
* dscGetEEPROM\(\) 
* dscGetReferenceVoltages\(\) 
* dscGetStatus\(\) 
* dscLEDTest\(\) 
* dscSetCalMux\(\) 
* dscSetEEPROM\(\) 
* dscSetReferenceVoltages\(\) 
* dscSetTrimDa\(\) 
* dscSetUserInterruptFunction\(\) 
* dscUserInt\(\)

