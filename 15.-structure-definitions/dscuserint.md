# DSCUSERINT

Structure containing configuration data for user interrupt operation.

### Structure Definition

```c
typedef struct {

    BYTE intsource;
    BYTE  counter
    BYTE  clksource
    FLOAT rate
    DWORD int_type
    DSCUserInterruptFunction func
    BOOL  Enable
    BOOL  Mode
    BOOL  BitSelect
    BOOL  Edge

} DSCUSERINT;
```

### Structure Members

| Name | Description | Applicable Boards |
| :--- | :--- | :--- |
| intsource | This field indicates the source of the interrupts. You may select USER\_INT\_SOURCE\_INTERNAL to use an on-board counter/timer, or USER\_INT\_SOURCE\_EXTERNAL to use an external clock. Refer to each board's user manual for details on the options for counter/timer and external clock. | Diamond-MM-32DX-AT,Diamond-MM-32X-AT,Onyx-MM,Diamond-MM-16-AT,Diamond-MM-16RP-AT |
| counter | If you choose intsource = USER\_INT\_SOURCE\_INTERNAL, you must specify which on-board counter you will be using to generate the interrupts. Each board has different valid options for clksource. | Diamond-MM-16-AT,Diamond-MM-16RP-AT,Diamond-MM-32DX-AT,Diamond-MM-32X-AT,Diamond-MM-AT |
| clksource | Selects the source of the clock that drives the on-boardcounter-timer when intsource = USER\_INT\_SOURCE\_INTERNAL. On Diamond-MM-32: 0 = internal 10MHz, 1 = internal 10kHz, 2 = external. On all other boards: 0 = internal, 1 = external. | Diamond-MM-16-AT,Diamond-MM-16RP-AT,Diamond-MM-32DX-AT,Diamond-MM-32X-AT,Diamond-MM-AT,P104-GPIO96,Helix ,DS-MPE-DAQ0804,DS-MPE-GPIO,Onyx-MM,Ruby-MM-1616,Zeta,Aries |
| rate | Required only when intsource = USER\_INT\_SOURCE\_INTERNAL. If you select a non-zero value, the on-board counter/timer will be programmed to generate interrupts at this rate. If this value is set to 0 then the dscUserInt function will not program the board's counter/timer with a new value, and will assume that the counter has been preprogrammed. This is useful if you want to control the counter/timer rate yourself. | Diamond-MM-16-AT,Diamond-MM-16RP-AT,Diamond-MM-32DX-AT,Diamond-MM-32X-AT,Diamond-MM-AT,Onyx-MM |
| int\_type | Returns the interrupt type that the driver attached the interrupt handler to. This depends on which board you are using, but will generally be INT\_TYPE\_DIO or INT\_TYPE\_COUNTER. | Diamond-MM-16-AT,Diamond-MM-16RP-AT,Diamond-MM-32DX-AT,Diamond-MM-32X-AT,Diamond-MM-AT,Onyx-MM |
| func | This is a reference pointer to the user interrupt function that was attached to the interrupt. This is usually passed in as a parameter to the dscUserInt \(\) function. | Diamond-MM-16-AT,Diamond-MM-16RP-AT,Diamond-MM-32DX-AT,Diamond-MM-32X-AT,Diamond-MM-AT,P104-GPIO96,DS-MPE-DAQ0804,DS-MPE-GPIO,Onyx-MM,Ruby-MM-1616,Zeta,Aries,Helix |
| Enable | 0 = disable interrupts, 1 = enable interrupts | DS-MPE-DAQ0804,Ruby-MM-1616,Zeta,Aries,Helix |
| Mode | 0 = alone, 1 = before standard function, 2 = after standard function | P104-GPIO96,DS-MPE-DAQ0804,DS-MPE-GPIO,Ruby-MM-1616,Zeta,Aries,Helix |
| BitSelect | To selects which DIO line to use to trigger interrupts | Helix,DS-MPE-DAQ0804,Zeta,Aries |
| Edge | 1 = rising edge, 0 = falling edge | Helix,DS-MPE-DAQ0804,Zeta,Aries |

