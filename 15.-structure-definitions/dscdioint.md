# DSCDIOINT

Structure containing interrupt-based Digital I/O settings. These settings determine the behavior of the interrupt-based D/A sampling operation. Please refer to the D/A interrupt description for complete explanation of interrupt behavior resulting from the various settings in this structure.

### Structure Definition

```c
typedef struct
{

    DWORD num_transfers
    BYTE port;
    BYTE size;
    BOOL cycle;
    BOOL internal_clock;
    DFLOAT rate;
    BYTE mode;
    BYTE source;
    BYTE* digital_values;
    DWORD fifo_depth;
    DWORD dump_threshold;
    void* IntFunc;
    BOOL Enable ;
    BOOL Polarity;
    BOOL Intclr;

} DSCDIOINT;
```

### Structure Members

| Name | Description |
| :--- | :--- |
| num\_transfers | Number of conversions to perform |
| port | for boards w/ &gt;8 bits of dio |
| size | 0-7 for bits 0-7, 8 for full byte, 16 for word |
| cycle | Set to TRUE to repeat the operation continuously |
| internal\_clock | Set to TRUE to use the internal clock as a trigger, FALSE to use an external trigger |
| rate | Rate for internal clock \(if used\) |
| mode | for Garnet only |
| source | for Onyx only |
| digital\_values | The array that holds the DIO values to send |
| fifo\_depth | FIFO depth \(threshold\) where interrupts are triggered |
| dump\_threshold | Threshold at which to dump the sample buffer |
| IntFunc | pointer to user function to run when interrupts occur |
| Enable | 8 bit data to enable edge detection on DIO port B; 1 = enable, 0 = disable |
| Polarity | 8 bit data to select the active edge for interrupt generation;1 = rising, 0 = falling |
| Intclr | 1 = interrupt handler should clear interrupt clear registers; 0 = interrupt handler should not clear interrupt clear registers |

