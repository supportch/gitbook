# DS-MPE-GPIO

### Overview

DS-MPE-GPIO is a rugged, low cost 36-channel digital I/O PCIe MiniCard module which is ideal for digital I/O expansion in embedded and OEM applications. An FPGA provides 36 buffered digital I/O lines that can be configured to operate in a simple I/O mode in the form of 8-bit and 4-bit ports, or in counter/timer and PWM modes. Two ports are fixed digital I/O ports with programmable direction in 8-bit groups. One port can be operated as either a 4-bit DIO or 4 counter/timers with 1 input and 1 output per counter. The other port can be operated as either 8 DIO or up to 8 pulse width modulators \(PWMs\). The DS-MPE-GPIO product comes with the 36-channel PCIe MiniCard digital I/O module, the CK-DAQ02 cable kit, and a hardware kit with jumpers and screws.

### Board Initialization

To use the DS-MPE-GPIO board in an appllication using the UD, the dscPCIInitBoard function should use the board macro DSC\_MPEGPIO. This is shown in the example below.

```c
dscPCIInitBoard( DSC_MPEGPIO , &dsccb, &board );
```

### I/O connectors

DS-MPE-GPIO provides 2 I/O connectors for the attachment of all user I/O signals. These connectors are shown below. The connectors are JST number BM20B-GHDS-G-TF. Diamond’s I/O cable number 6980501 \(2 per board\) is used to connect the user’s signals to these connectors. This cable comes in a kit of 2 as part number CK-DAQ02. This cable has a common 2mm pitch IDC connector at the opposite end which may be plugged into a custom board or may be cut off and the wiring then used as needed. Unused signals do not need to be terminated. However if the cable wiring is cut, care should be taken to avoid shorting any unused wires to any other voltages in the system in order to prevent possible damage to the board or incorrect I/O readings.

### Digital I/O

There are 36 digital I/O signals, divided into six groups as DIOA0- DIOA7, DIOB0- DIOB5, DIOC0- DIOC3, DIOD0- DIOD7, DIOE0- DIOE5 and DIOF0- DIOF3. Ports A-C signals \(DIOA0- DIOA7, DIOB0- DIOB5, DIOC0- DIOC3\) are on I/O connector J1 and ports D-F signals \(DIOD0- DIOD7, DIOE0- DIOE5 and DIOF0- DIOF3\) are on connector J2. Digital I/O signals use 3.3V signaling only. Each signal’s direction of ports C and F are independently programmable, whereas Ports A, B, D, E are byte wise programmable. On system startup or reset, all signals are automatically set to input mode. All digital I/O signals have programmable pull-up/down resistors and are divided into two groups for this purpose. Group A includes I/O signals ports A to C and Group B includes I/O signals ports D to F. All signals within each group have the same pull direction. The default configuration for DS-MPE-GPIO is for all DIO signals to be pulled low.

### MPE-GPIO Universal Driver Functions

* dscCancelOp\(\) 
* dscCounterConfig\(\) 
* dscCounterRate\(\) 
* dscCounterRead\(\) 
* dscCounterReset\(\) 
* dscDIOInputBit\(\) 
* dscDIOInputByte\(\) 
* dscDIOOutputBit\(\) 
* dscDIOOutputByte\(\) 
* dscDIOSetConfig\(\) 
* dscLEDTest\(\) 
* dscPWMClear\(\) 
* dscPWMStart\(\) 
* dscSpecialFunction\(\) 
* dscUserInt\(\) 
* dscUserIntRun\(\)

