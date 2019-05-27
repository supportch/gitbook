# Diamond-MM-16-AT

### Board Initialization

To use the DMM-16-AT board in an appllication using the UD, the dscInitBoard function should use the board macro DSC\_DMM16. This is shown in the example below.

```c
dscInitBoard( DSC_DMM16, &dsccb, &board );
```

### Analog Input

|  |  |
| :--- | :--- |
| Max Input Channels: | 16 \(single-ended\) or 8 \(differential\) |
| A/D Resolution: | 16 bits \(1/65536 of full-scale\) |
| Data range: | -32768 to +32767 for all voltage ranges |
| Input Ranges \(Bipolar\): | ±10V, ±5V, ±2.5V, or ±1.25V |
| Input Ranges \(Unipolar\): | 0-10V, 0-5V, or 0-2.5V |
| Supported Conversion Triggers: | Software, Internal Clock, or External TTL Signal |
| Maximum Conversion Rate \(Software Command\): | 2,000 \(approx.\) samples per second |
| Maximum Conversion Rate \(Interrupt Routine w/FIFO\): | 100,000 samples per second |
| FIFO: | 512 samples with fixed threshold of 256 |

This board supports the following programmable input ranges and resolutions:

{% tabs %}
{% tab title="A/D Ranges" %}
| Code | Range | ADBU | G1 | G0 | Input Range | Resolution \(1 LSB\) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 0 | 0 | 0 | 0 | 0 | ±5V | 153μV |
| 1 | 0 | 0 | 0 | 1 | ±2.5V | 76μV |
| 2 | 0 | 0 | 1 | 0 | ±1.25V | 38μV |
| 3 | 0 | 0 | 1 | 1 | Invalid Setting | - |
| 4 | 0 | 1 | 0 | 0 | Invalid Setting | - |
| 5 | 0 | 1 | 0 | 1 | Invalid Setting | - |
| 6 | 0 | 1 | 1 | 0 | Invalid Setting | - |
| 7 | 0 | 1 | 1 | 1 | Invalid Setting | - |
| 8 | 1 | 0 | 0 | 0 | ±10V | 305μV |
| 9 | 1 | 0 | 0 | 1 | ±5V | 153μV |
| 10 | 1 | 0 | 1 | 0 | ±2.5V | 76μV |
| 11 | 1 | 0 | 1 | 1 | ±1.25V | 38μV |
| 12 | 1 | 1 | 0 | 0 | 0 - 10V | 153μV |
| 13 | 1 | 1 | 0 | 1 | 0 - 5V | 76μV |
| 14 | 1 | 1 | 1 | 0 | 0 - 2.5V | 38μV |
| 15 | 1 | 1 | 1 | 1 | Invalid Setting | - |
{% endtab %}
{% endtabs %}

NOTE: The A/D modes for codes 3 through 7 and 15 are invalid, and the settings for codes 9 through 11 are identical to codes 0 through 2.

### Analog Output \(model DMM-16-AT only\)

|  |  |
| :--- | :--- |
| Max Output Channels: | 4 |
| D/A Resolution: | 12 bits \(1/4096 of full-scale\) |
| Data range: | 0 to 4095 for all voltage ranges |
| Output Ranges \(Bipolar, Fixed\): | ±5V |
| Output Ranges \(Bipolar, Programmable\): | ±1V to ±10V |
| Output Ranges \(Unipolar, Fixed\): | 0-5V |
| Output Ranges \(Unipolar, Programmable\): | 0-1V to 0-10V |

### Digital I/O

|  |  |
| :--- | :--- |
| Max Input Ports: | 1 \(1 byte or 8 bits\), TTL compatible, no readback capability |
| Max Output Ports: | 1 \(1 byte or 8 bits\), TTL compatible |

Digital I/O lines on Diamond-MM-16-AT are fixed direction and do not require configuration prior to use.

### Diamond-MM-16-AT Universal Driver Functions

* dscADAutoCal\(\) 
* dscADCalVerify\(\) 
* dscADSample\(\) 
* dscADSampleInt \(\) 
* dscADScan\(\) 
* dscADScanInt\(\) 
* dscADSetChannel\(\) 
* dscADSetSettings\(\) 
* dscClearUserInterruptFunction\(\) 
* dscCounterDirectSet\(\) 
* dscCounterRead\(\) 
* dscCounterSetRate\(\) 
* dscCounterSetRateSingle\(\) 
* dscDAAutoCal\(\) 
* dscDACalVerify\(\) 
* dscDAConvert\(\) 
* dscDAConvertScan\(\) 
* dscDAConvertScanInt\(\) 
* dscDIOClearBit\(\) 
* dscDIOInputBit\(\) 
* dscDIOInputByte\(\) 
* dscDIOOutputBit\(\) 
* dscDIOOutputByte\(\) 
* dscDIOSetBit\(\) 
* dscGetEEPROM\(\) 
* dscGetReferenceVoltages\(\) 
* dscGetStatus\(\) 
* dscSetEEPROM\(\) 
* dscSetReferenceVoltages\(\) 
* dscSetUserInterruptFunction\(\) 
* dscUserInt\(\)

