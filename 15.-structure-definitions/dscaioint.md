# DSCAIOINT

Structure containing interrupt-based analog I/O settings. These settings determine the behavior of the interrupt-based A/D sampling operation. Please refer to the A/D interrupt description for complete explanation of interrupt behavior resulting from the various settings in this structure.

### Structure Definition

```c
typedef struct { 

    DWORD num_conversions; 
    FLOAT conversion_rate; 
    FLOAT conversion_rate_final
    BOOL cycle; 
    BOOL internal_clock; 
    BYTE low_channel; 
    BYTE high_channel; 
    BOOL external_gate_enable; 
    BOOL internal_clock_gate; 
    DSCSAMPLE* sample_values; 
    BOOL fifo_enab; 
    WORD fifo_depth; 
    DWORD dump_threshold; 
    BYTE clksource; 
    BOOL FIFOThreshold;
    
} DSCAIOINT;
```

| Name | Description | Applicable Boards |
| :--- | :--- | :--- |
| num\_conversions | In one-shot mode \(cycle = 0\), this is the maximum number of A/D or D/A conversions to perform. In recycle mode, this is the buffer size. | Aries, Diamond-MM-16-AT, Diamond-MM-16RP-AT, Diamond-MM-32DX-AT, Diamond-MM-32X-AT, Diamond-MM-AT, Helix,DS-MPE-DAQ0804, Zeta |
| conversion\_rate | The desired rate at which single conversions \(sample mode\) or scans \(scan mode\) should occur. In most cases the input clock is 10MHz. This signal is divided by an integer value to obtain the desired sample rate. Because of the integer arithmetic, not all sample rates are obtainable. The driver will select the closest possible rate. | Diamond-MM-16-AT, Diamond-MM-16RP-AT, Diamond-MM-32DX-AT, Diamond-MM-32X-AT, Diamond-MM-AT |
| conversion\_rate\_final | OUTPUT: the actual conversion rate programmed into the clock | Diamond-MM-16-AT, Diamond-MM-16RP-AT, Diamond-MM-32DX-AT, Diamond-MM-32X-AT, Diamond-MM-AT |
| cycle | If TRUE, the function will perform A/D or D/A conversions repeatedly. When the current number of transfers reaches the number set in num\_conversions, The process will continue. The buffer pointer will be reset to the beginning of the buffer and new data will overwrite old data. If FALSE, the function will take the number of samples specified by num\_conversions and then terminate. | Aries, Diamond-MM-16-AT, Diamond-MM-16RP-AT, Diamond-MM-32DX-AT, Diamond-MM-32X-AT, Diamond-MM-AT, Helix,DS-MPE-DAQ0804, Zeta |
| internal\_clock | TRUE = use the board's internal clock to generate interrupts. FALSE = use the external clock \(source pin depends on the board\). | Diamond-MM-16-AT, Diamond-MM-16RP-AT, Diamond-MM-32DX-AT, Diamond-MM-32X-AT, Diamond-MM-AT |
| low\_channel | The starting channel of the channel range on which to perform A/D or D/A conversions. | Diamond-MM-16-AT, Diamond-MM-16RP-AT, Diamond-MM-32DX-AT, Diamond-MM-32X-AT, Diamond-MM-AT |
| high\_channel | The ending channel of the channel range on which to perform A/D conversions. | Diamond-MM-16-AT, Diamond-MM-16RP-AT, Diamond-MM-32DX-AT, Diamond-MM-32X-AT, Diamond-MM-AT |
| external\_gate\_enable | This parameter defines the control bit C2 on boards DMM, DMM-16, DMM-AT, and DMM-16-AT. It is used to enable an external signal on pin 29 \(In0-\) of the boards I/O connector, which provides a gating control for A/D sampling when an external clock is used to control the sample rate. If enabled, a high level on In0- will enable the sampling to run, and a low level will halt sampling. TRUE = use the external signal IN0- to gate the external sampling clock. FALSE = No gating is enabled and sampling continues uninterrupted. See sections regarding C2, In0-, and DIO in the board-specific manuals for more details. | Diamond-MM-16-AT, Diamond-MM-16RP-AT, Diamond-MM-32DX-AT, Diamond-MM-32X-AT, Diamond-MM-AT |
| internal\_clock\_gate | This parameter defines the control bit C0 on boards DMM, DMM-16, DMM-AT, and DMM-16-AT. It is used to enable an external signal on pin 48 \(Din0\) of the boards' I/O connector to provide a gating control for A/D sampling when the internal clock is used to control the sample rate. If enabled, a high level on Din0 will enable the sampling to run, and a low level will halt sampling. On the DMM-32-AT this will set GT12EN high. In general: TRUE = Use an external signal to gate the internal sampling clock, while FALSE = No gating is enabled and sampling continues uninterrupted. | Diamond-MM-16-AT, Diamond-MM-16RP-AT, Diamond-MM-32DX-AT, Diamond-MM-32X-AT, Diamond-MM-AT |
| sample\_values | Pointer to a buffer holding either the results of the A/D conversions or the output codes to use in D/A conversions. | Aries,Diamond-MM-16-AT, Diamond-MM-16RP-AT, Diamond-MM-32DX-AT, Diamond-MM-32X-AT, Diamond-MM-AT, Helix,DS-MPE-DAQ0804, Zeta |
| fifo\_enab | If TRUE, will use the on-board FIFO in analog input operations. Used only on DMM-AT, DMM-16-AT, and DMM-32. | Aries, Diamond-MM-16-AT, Diamond-MM-16RP-AT, Diamond-MM-32DX-AT, Diamond-MM-32X-AT, Diamond-MM-AT, Helix, DS-MPE-DAQ0804, Zeta |
| fifo\_depth | The number of A/D samples to store in the FIFO before generating an interrupt request. | Aries, Diamond-MM-32DX-AT, Diamond-MM-32X-AT, Diamond-MM-AT |
| dump\_threshold | The number of A/D conversions to perform before copying the driver's sample buffer to the user-accessible buffer. | Diamond-MM-16-AT, Diamond-MM-16RP-AT, Diamond-MM-32DX-AT, Diamond-MM-32X-AT, Diamond-MM-AT |
| clksource | \(Prometheus only\) Selects the clock source for counter/timer 1 during D/A conversions. 1 = 10MHz, 0 = 100KHz. | Aries |
| FIFOThreshold | 0-2048, indicates level at which FIFO will generate an interrupt if FIFOEnable = 1 | Helix, DS-MPE-DAQ0804, Zeta |

