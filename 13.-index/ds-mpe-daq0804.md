# DS-MPE-DAQ0804

### Overview

DS-MPE-DAQ0804 is a rugged data acquisition PCIe MiniCard module consisting of both analog and configurable digital I/O. The module is ideal for add-on data acquisition I/O expansion in embedded and OEM applications. The PCIe MiniCard offers 8 single ended or four differential 16-bit analog inputs with an aggregate sample rate of 100KHz maximum, 2048 sample A/D FIFO, four 16-bit analog outputs, and 14 digital I/O lines. The buffered digital I/O lines can be optionally configured as either pulse width modulators or counter/timers.

Diamond’s Universal Driver 8.1.0 software provides driver support for all functions. The DS-MPE-DAQ0804 product comes with the PCIe MiniCard data acquisition I/O module, the CK-DAQ0804 cable kit, and a hardware kit with jumpers and screws.

### Board Initialization

To use the DS-MPE-DAQ0804 board in an appllication using the UD, the dscPCIInitBoard function should use the board macro DSC\_MPEDAQ0804. This is shown in the example below.

```c
dscPCIInitBoard(DSC_MPEDAQ0804 , &dsccb, &board );
```

### A/D Features

|  |
| :--- |
| 16 analog voltage inputs |
| 16-bit resolution \(1 part in 65536\) |
| Programmable input ranges: 0-5V, 0-10V, +/-5v, +/-10V |
| Single-ended and differential input configuration options |
| Precision, low-drift 2.5V reference voltage |
| 100KHz maximum total A/D sample rate \(all active channels combined\) |
| Integrated 2048-sample FIFO and interrupt service for efficient high-speed sampling |

### D/A Features

|  |
| :--- |
| 4 analog voltage outputs |
| 16-bit resolution \(1 part in 65536\) |
| Single-channel and multi-channel simultaneous update modes |
| Programmable output range: 0-5V, 0-2.5V |
| 30KHz update rate capability |
| Waveform generator on 1 to 4 outputs with user-defined waveforms and 2048-sample waveform buffer |

### Digital I/O features

|  |
| :--- |
| 21 digital I/O lines |
| 3.3V logic levels |
| User-configurable 10K pull-up / pull-down resistors |
| Individually programmable direction for each line |
| 8-bit programmable edge detection circuit |
| Buffers for protection and higher current drive |
| 8 32-bit counter/timers with up counting, down counting, pulse output, and interrupt features |
| 4 24-bit pulse-width modulators with programmable duty cycle and output polarity |
| Interrupt support for A/D, digital I/O, and counter/timer circuits |

### DS-MPE-DAQ0804 Universal Driver Functions

* dscADIntCancel\(\) 
* dscADIntStatus\(\) 
* dscADSample\(\) 
* dscADSampleInt\(\) 
* dscADScan\(\) 
* dscADSetSettings\(\) 
* dscADSetTiming\(\) 
* dscCancelOp\(\) 
* dscCounterConfig\(\) 
* dscCounterRate\(\) 
* dscCounterRead\(\) 
* dscCounterReset\(\) 
* dscDAConvert\(\) 
* dscDAConvertScan\(\) 
* dscDASetSettings\(\) 
* dscDIOInputBit\(\) 
* dscDIOInputByte\(\) 
* dscDIOOutputBit\(\) 
* dscDIOOutputByte\(\) 
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

