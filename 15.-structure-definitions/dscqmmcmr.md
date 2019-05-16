# DSCQMMCMR

Structure containing configuration data for the Counter Mode Register of a counter on the 9513 chip on Quartz-MM. Each counter on each chip has its own Counter Mode Register. The Counter Mode Register must be programmed before using the counter.

### Structure Definition

```c
typedef struct {

    BYTE counter;
    BYTE gating_control;
    BYTE active_source_edge;
    BYTE count_source;
    BYTE special_gate;
    BYTE reload_source;
    BYTE cycle;
    BYTE count_type;
    BYTE count_direction;
    BYTE output_control;

} DSCQMMCMR;
```

### Structure Members

| Name | Description |
| :--- | :--- |
| counter | Counter number: 1-5 for QMM-5, 1-10 for QMM-10 |
| gating\_control | Gating control is the means by which the counter is enabled or disabled in hardware. TCn-1 means the terminal count state of the counter one lower in number. When TCn-1 is specified, the counter will only count when the lower-numbered counter is in its terminal count state and a source edge is applied to the selected counter source. Specifying TCn-1 for counter 1, as well as counter 6 in QMM-10, is invalid, since in these cases counter n-1 does not exist. Specifying TCn-1 as the gating control allows several consecutive counters to be cascaded to form a wider counter in multiples of 16 bits. For example, counters 1 and 2 can be cascaded together to form a 32-bit-wide counter by specifying no gating for counter 1 and TCn-1 for counter 2, and setting both counters to the same input source. Specifying edge gating causes the counter to be triggered on the first matching edge after the counter is armed. In some modes, only the first such edge affects the counter; in other modes, successive edges also affect operation. Select from the gating control macros in above list |
| active\_source\_edge | Active edge for the counter: 0 = rising edge, 1 = falling edge |
| count\_source | Counter source. Note that each counter may take its source from any of the source pins, any of the gate pins, and several other inputs. There is no fixed relationship between counter n, source n, and gate n. Counters may share the same source and gate pins. Select from counter source macros in above list |
| special\_gate | Special gate function; refer to the 9513 datasheet for details. 0 = enable, 1 = disable |
| reload\_source | The source of the data that will be used to reload the counter when it reaches terminal count. 0 = Load register; 1 = Load or Hold register \(depends on the counter configuration\) |
| cycle | Selects either one-shot or recycle mode. In one-shot mode, the counter counts once to terminal count \(TC\) and then automatically disarms. In recycle mode the counter reloads from the selected reload source when it reaches TC and continues repeatedly until it is disarmed. 0 = one-shot, 1 = recycle |
| count\_type | Selects binary or BCD \(binary coded decimal\) counting mode. In binary mode each 16-bit counter has a maximum count value of 65535. In BCD mode each 4-bit nybble represents a digit from 0-9, and the maximum count is 9999. in BCE mode, a count of 99 will be represented by the binary no. 0000 0000 1001 1001 or 153 in standard notation. 0 = binary, 1 = BCD |
| count\_direction | Selects up or down counting; 0 = down, 1 = up |
| output\_control | Determines the behavior of the counter's output pin. Specifying Toggle mode causes the output of the counter to generate a square wave with 50 percent duty cycle \(high and low periods equal in duration\) when the counter is in repetitive count mode. In Toggle mode, each high and low level lasts for one entire count period, and the output changes state on each TC until the counter is disarmed. Specifying TC pulse causes the counter to output a pulse of the selected polarity equal to one period of the counter's input source. If the counter is being used as a totalizer and the output is not important, it can be specified as inactive, output low, or high impedance. Select from output control macros in above list. |

