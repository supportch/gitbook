# DSCQMMMMR

Structure containing configuration data for the Quartz-MM Master Mode Register. Each 9513 chip has its own master mode register. The master mode register must be programmed before any counter on that chip can be used.

### Structure Definition

```c
typedef struct {

    BYTE counter_group;
    BYTE fout_divider;
    BYTE fout_source;
    BYTE compare1_enable;
    BYTE compare2_enable;
    BYTE tod_mode;

} DSCQMMMMR;
```

### Structure Members

| Name | Description |
| :--- | :--- |
| counter\_group | The control code to write to or read from the control word register. |
| fout\_divider | Divider for the 9513 chip's internal frequency generator; range is 1-16. The output frequency of the fout pin is fout\_source / fout\_divider. The fout \(frequency output\) pin from counter chip 1 is available on pin 31 of the board's I/O header and may be used by counters 1-5. The fout signal from chip 2 is not available externally but may be used within the chip by counters 6-10. |
| fout\_source | Source frequency for the 9513 chip's internal frequency generator. Follow link to the macro list below to select. |
| compare1\_enable | TRUE = Enable the comparator on counter 1; FALSE = disabled. |
| compare2\_enable | TRUE = Enable the comparator on counter 2; FALSE = disabled. The comparator function allows the use of counters 1 and 2 on each 9513 chip as totalizers with alarm outputs. When the count of any counter whose comparator is enabled equals the value programmed in that counter's alarm register, the counter output will be true, otherwise it will be false. The alarm register is programmed with function dscQMMSpecialCounterFunction. |
| tod\_mode | Time-of-day mode; select from time-of-day macros by following the QMM Macros link below. The time-of-day circuit is intended to be used with an input frequency of 50Hz, 60Hz, or 100Hz. The divider of 5, 6, or 10 is chosen to match the input frequency and provide a 0.1 second resolution. On a CPU with a built-in real-time clock, the time-of-day circuit is generally not needed. |

