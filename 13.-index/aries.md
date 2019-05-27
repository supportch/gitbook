# Aries

### Overview

Aries is an embedded single board computer \(SBC\) with a PC/104-Plus form factor. Aries integrates on-board memory, PC/104-Plus \(ISA + PCI\) expansion, one PCIe MiniCard socket, dual Gigabit Ethernet, and optional data acquisition circuit with analog and digital I/O.

The Aries SBC is based on Intel “Bay Trail” E3800 series processors. The form factor is similar to PC/104 with left and right side extensions that extend the full length of the two sides without providing the corners traditionally seen in PC/104 boards with “wings”.

### Board Initialization

To use the Aries board in an appllication using the UD, the dscInitBoard function should use the board macro DSC\_ARIES. This is shown in the example below... 

The base address should be 0x280 and the default IRQ to use is IRQ 5. 

```c
dscInitBoard(DSC_ARIES, &dsccb, &board );
```

### Analog Input

|  |  |
| :--- | :--- |
| Max Input Channels: | 16 \(single-ended\) or 8 \(differential\)  |
| A/D Resolution: | 16 bits \(1/65536 of full-scale\)  |
| Data range: | -32768 to +32767 for all voltage ranges |
| Input Ranges \(Bipolar\): | ±10V, ±5V, ±2.5V, or ±1.25V  |
| Input Ranges \(Unipolar\): | 0-10V, 0-5V, or 0-2.5V  |
| Supported Conversion Triggers: | Software, External digital signal  |
| Maximum Conversion Rate \(Software Command\): | approx. 250,000 samples per second, depending on code and operating system |
| Maximum Conversion Rate \(Interrupt Routine w/FIFO\): | 100,000 samples per second |
| FIFO: |  2048 samples with Programmable interrupt threshold |

### Analog Output

|  |  |
| :--- | :--- |
| Max Output Channels: | 4 |
| D/A Resolution: | 15 bits \(1/65536 of full scale\)  |
| Data range: | 0 to 65535 for all voltage ranges |
| Bipolar Output Ranges: | ±10V, ±5V, ±2.5V |
| Unipolar Output Ranges: | 0-10V, 0-5V |

### Digital I/O

<table>
  <thead>
    <tr>
      <th style="text-align:left"></th>
      <th style="text-align:left"></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Max Ports:</td>
      <td style="text-align:left">
        <p>3, bi-directional, programmable in 8-bit groups.Digital I/O ports on Prometheus
          require direction to be set with DscDIOSetConfig() before use.</p>
        <p>All DIO lines power-up in input mode and have readback capability.</p>
        <p>All DIO lines have r external configurable pull esistors that can be configured
          for all pull-up or all pull-down with a jumper.</p>
      </td>
    </tr>
  </tbody>
</table>###  Aries Universal Driver Functions

* [dscADAutoCal\(\) ](../14.-universal-driver-apis/dscadautocal.md)
* [dscADCalVerify\(\)](../14.-universal-driver-apis/dscadcalverify.md) 
* [dscADClockConfig\(\) ](../14.-universal-driver-apis/dscadclockconfig.md)
* [dscADIntCancel\(\)](../14.-universal-driver-apis/dscadintcancel.md) 
* [dscADIntStatus\(\) ](../14.-universal-driver-apis/dscadintstatus.md)
* [dscADSample\(\) ](../14.-universal-driver-apis/dscadsample.md)
* [dscADSampleInt \(\) ](../14.-universal-driver-apis/dscadsampleint.md)
* [dscADScan\(\) ](../14.-universal-driver-apis/dscadscan.md)
* [dscADSetSettings\(\)](../14.-universal-driver-apis/dscadsetsettings.md) 
* [dscCancelOpType\(\)](../14.-universal-driver-apis/dsccanceloptype.md) 
* [dscCounterConfig\(\)](../14.-universal-driver-apis/dsccounterconfig.md) 
* [dscCounterFunction\(\) ](../14.-universal-driver-apis/dsccounterfunction.md)
* [dscCounterRate\(\)](../14.-universal-driver-apis/dsccounterrate.md) 
* [dscCounterRead\(\)](../14.-universal-driver-apis/dsccounterread.md) 
* [dscCounterReset\(\)](../14.-universal-driver-apis/dsccounterreset.md) 
* [dscDAConvert\(\)](../14.-universal-driver-apis/dscdaconvert.md) 
* [dscDAConvertScan\(\)](../14.-universal-driver-apis/dscdaconvertscan.md) 
* [dscDASetSettings\(\)](../14.-universal-driver-apis/dscdasetsettings.md) 
* [dscDASetSim\(\)](../14.-universal-driver-apis/dscdasetsim.md) 
* [dscDIOInputBit\(\)](../14.-universal-driver-apis/dscdioinputbit.md) 
* [dscDIOInputByte\(\) ](../14.-universal-driver-apis/dscdioinputbyte.md)
* [dscDIOOutputBit\(\) ](../14.-universal-driver-apis/dscdiooutputbit.md)
* [dscDIOOutputByte\(\)](../14.-universal-driver-apis/dscdiooutputbyte.md) 
* [dscDIOSetConfig\(\)](../14.-universal-driver-apis/dscdiosetconfig.md) 
* [dscLEDTest\(\) ](../14.-universal-driver-apis/dscledtest.md)
* [dscPWMClear\(\)](../14.-universal-driver-apis/dscpwmclear.md) 
* [dscPWMStart\(\)](../14.-universal-driver-apis/dscpwmstart.md) 
* [dscPauseOp\(\)](../14.-universal-driver-apis/dscpauseop.md) 
* [dscResumeOp\(\)](../14.-universal-driver-apis/dscresumeop.md) 
* [dscSpecialFunction\(\)](../14.-universal-driver-apis/dscspecialfunction.md) 
* [dscUserInt\(\)](../14.-universal-driver-apis/dscuserint.md) 
* [dscUserIntRun\(\) ](../14.-universal-driver-apis/dscuserintrun.md)
* [dscWGBufferLoad\(\)](../14.-universal-driver-apis/dscwgbufferload.md) 
* [dscWGCommand\(\)](../14.-universal-driver-apis/dscwgcommand.md) 
* [dscWGConfigSet\(\)](../14.-universal-driver-apis/dscwgconfigset.md) 
* [dscWatchdogConfig\(\)](../14.-universal-driver-apis/dscwatchdogconfig.md) 
* [dscWatchdogDisable\(\)](../14.-universal-driver-apis/dscwatchdogdisable.md) 
* [dscWatchdogEnable\(\)](../14.-universal-driver-apis/dscwatchdogenable.md) 
* [dscWatchdogTrigger\(\)](../14.-universal-driver-apis/dscwatchdogtrigger.md)

