# DSCWATCHDOG

### Structure Definition

```c
typedef struct {
 
    WORD wd1; 
    BYTE wd2; 
    BYTE options; 
    BYTE HardwareTriggerEnable; 
    BYTE EdgeSelection; 
    BYTE CountEarly ; 
    BYTE InterruptEnable; 
    Void (*IntFunc) (void *parameter); 
    
    } DSCWATCHDOG;
```

### Structure Members

| Name | Description |
| :--- | :--- |
| WD1 | 16-bit timer value \(runs at ~32KHz - max 2 seconds\) |
| WD2 | 8-bit timer value \(runs at ~32KHz - max 7.2ms\) |
| options | mask PROM\_WD\_TRIGGER\_SMI PROM\_WD\_TRIGGER\_NMI HERC\_WD\_TRIGGER\_SMI HERC\_WD\_TRIGGER\_NMI ATHENA\_WD\_TRIGGER\_SMI |
| HardwareTriggerEnable | 0 = disable, 1 = enable |
| EdgeSelection | if HardwareTriggerEnable = 1, then 0 = Raising edge 1 = falling edge |
| CountEarly | 0 = disable, 1 = enable i.e. DIO C4 goes high when counter A = 1 instead of 0 , This enables C4 to be externally wired to C5 to cause an automatic repetitive retrigger when WDIEN = 1 and WDEDGE = 0 |
| InterruptEnable | 1= when counter A reaches 0 an interrupt will occur, 0=interrupt will not occur |
| IntFunc | pointer to user function to run when interrupts occur |

