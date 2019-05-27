# Diamond-MM-AT

### Board Initialization

To use the DMM-AT board in an appllication using the UD, the dscInitBoard function should use the board macro DSC\_DMM. This is shown in the example below.

```c
dscInitBoard( DSC_DMM , &dsccb, &board );
```

### Analog Input

|  |  |
| :--- | :--- |
| Max Input Channels: | 16 \(single-ended\) or 8 \(differential\) |
| A/D Resolution: | 12 bits \(1/4096 of full-scale\) |
| Data range: | 0 to 4095 for all voltage ranges |
| Input Ranges \(Bipolar\): | ±10V, ±5V, ±2.5V, ±1V, ±0.5V, or Custom |
| Input Ranges \(Unipolar\): | 0-10V, 0-5V, 0-2.5V, 0-1V, or Custom |
| Supported Conversion Triggers: | Software, Internal Clock, or External TTL Signal |
| Maximum Conversion Rate \(Software Command\): | 2,000 \(approx.\) samples per second |
| Maximum Conversion Rate \(Interrupt Routine w/FIFO\): | 100,000 samples per second |
| FIFO: | 512 samples with fixed threshold of 256 |

This board supports the following programmable input ranges and resolutions:

{% tabs %}
{% tab title="A/D Ranges" %}
| Code | Range | ADBU | G1 | G0 | Input Range | Resolution \(1 LSB\) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 0 | 0 | 0 | 0 | 0 | ±5V | 2.44mV |
| 1 | 0 | 0 | 0 | 1 | ±2.5V | 1.22mV |
| 2 | 0 | 0 | 1 | 0 | ±1.25V | 0.61mV |
| 3 | 0 | 0 | 1 | 1 | ±0.625V | 0.305mV |
| 4 | 0 | 1 | 0 | 0 | 0 - 10V | 2.44mV |
| 5 | 0 | 1 | 0 | 1 | 0 - 5V | 1.22mV |
| 6 | 0 | 1 | 1 | 0 | 0 - 2.5V | 0.61mV |
| 7 | 0 | 1 | 1 | 1 | 0 - 1.25V | 0.305mV |
| 8 | 1 | 0 | 0 | 0 | ±10V | 4.88mV |
| 9 | 1 | 0 | 0 | 1 | ±5V | 2.44mV |
| 10 | 1 | 0 | 1 | 0 | ±2.5V | 1.22mV |
| 11 | 1 | 0 | 1 | 1 | ±1.25V | 0.61mV |
| 12 | 1 | 1 | 0 | 0 | Invalid Setting | - |
| 13 | 1 | 1 | 0 | 1 | Invalid Setting | - |
| 14 | 1 | 1 | 1 | 0 | Invalid Setting | - |
| 15 | 1 | 1 | 1 | 1 | Invalid Setting | - |
{% endtab %}
{% endtabs %}

NOTE: Ranges 9 through 11 are identical to ranges 0 through 2.

### Analog Output

|  |  |
| :--- | :--- |
| Max Output Channels: | 2 |
| D/A Resolution: | 12 bits \(1/4096 of full-scale\) |
| Data range: | 0 to 4095 |
| Output Ranges \(Fixed\): | 0-5V |
| Output Ranges \(Programmable\): | 0-1V to 0-10V |

### Digital I/O

|  |  |
| :--- | :--- |
| Max Input Ports: | 1 \(1 byte or 8 bits\), TTL compatible, no readback capability |
| Max Output Ports: | 1 \(1 byte or 8 bits\), TTL compatible |

Digital I/O lines on Diamond-MM-AT are fixed direction and do not require configuration prior to use.

### Diamond-MM-AT Universal Driver Functions

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

