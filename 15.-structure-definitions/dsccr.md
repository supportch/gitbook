# DSCCR

Structure containing information on all counters. This is used for functions operating on 82C54 counters \(all boards except Quartz-MM\).

### Structure Definition

```c
typedef struct {

    BYTE control_code;
    BYTE counter_number;
    DWORD counter_data;
    DSCCS counter0;
    DSCCS counter1;
    DSCCS counter2;
    BYTE control_bit;
    DSCCS counter[DSC_DIO_PORTS_MAX];
    BOOL CtrClock;
    BOOL CtrOutEn;
    BOOL CtrOutPol;
    BOOL CtrCountDir;
    BOOL CtrReload;
    FLOAT Rate;
    BOOL ctrOutWidth;
    BOOL CtrCmd;
    BOOL CtrCmdData;
    FLOAT ActRate;
    BOOL Start;
    BOOL GateEn;
    
} DSCCR;
```

### Structure Members

| Name | Description |
| :--- | :--- |
| control\_code | Control code to write to or read from the control word register |
| counter\_number | Selected counter, 0-2 |
| counter\_data | Counter divisor value, 0-65535 |
| counter0 | Status and data read from counter 0 |
| counter1 | Status and data read from counter 1 |
| counter2 | Status and data read from counter 2 |
| control\_bit | Used in conjunction with control\_code |
| counter\[DSC\_DIO\_PORTS\_MAX\] | Counter-Max data read - used in fpgpio96 since there are 8 counters |
| CtrClock | Clock source |
| CtrOutEn | Enable and disable output onto corresponding I/O pin |
| CtrOutPol | Output pulses high or low only used if CtrOutEn = 1 |
| CtrCountDir | Setting counter direction |
| CtrReload | Setting auto reload |
| Rate | Desired output rate, Hz |
| ctrOutWidth | Counter output width in terms of clock |
| CtrCmd | Counter commands |
| CtrCmdData | Auxiliary data for counter command |
| ActRate | Actual rate resulting from the closest divisor available for the desired rate |
| Start | To start the counter |
| GateEn | To enable external gate in RMM1616 |

