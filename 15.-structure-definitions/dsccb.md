# DSCCB

Structure containing hardware settings for the current board. Some elements are unique to particular boards.

### Structure Definition

```c
typedef struct { 

    BYTE boardtype; 
    DSCB boardnum; 
    WORD base_address; 
    BYTE int_level; 
    BOOL RMM_external_trigger; 
    BOOL RMM_external_trigger_c3; 
    WORD EMM_IOAddr[8]; 
    WORD EMM_Interrupt[8]; 
    BYTE clkfrq0; 
    BYTE clkfrq1; 
    BYTE clksel1; 
    WORD address_space; 
    BYTE DAC_Config; // ONLY USED FOR DMM32DX 
    
    } DSCCB;
```

### Structure Members

| Name | Description |
| :--- | :--- |
| boardtype | The board type constant; automatically filled by dscInitBoard; |
| boardnum | The handle to the board; automatically filled in by dscInitBoard |
| base\_address | Base address of the board; refer to the board's user manual for valid base address settings |
| int\_level | Interrupt level of the board; used for boards with only one IRQ. |
| RMM\_external\_trigger | Enable or disable the external trigger; Used only on RMM416 and RMM1612 |
| RMM\_external\_trigger\_c3 | Enable or disable the external trigger; RMM416- and RMM1612-specific |
| EMM\_IOAddr\[8\] | I/O addresses for up to eight ports; EMM8-specific |
| EMM\_Interrupt\[8\] | Interrupts for up to eight ports; EMM8-specific |
| clkfrq0 | Frequency for on-board counter 0; used only on Prometheus; 0 = 10 MHz, 1= 1 MHz; |
| clkfrq1 | Frequency for on-board counter 1; used only on Prometheus; 0 = 10 MHz, 1= 100KHz; |
| clksel1 | 0 = internal oscillator with frequency set by clkfrq1, 1= external clock input CLK1; used only on Prometheus |
| address\_space | Size of I/O block in bytes to allocate. Only needed for DSC\_RAW board type. |
| DAC\_Config | Resolution of the DAC to use in the code. If this flag is set to 0, the driver will always use the DAC as a 12 bit DAC - This helps for backward compatibility. When set to 1, 16 bit DAC will be used. This is only used by the DMM32DX board.For all other boards this field is ignored |

