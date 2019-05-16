# DSCQMMPWM

Structure containing configuration data for pulse width modulation function on Quartz-MM. The structure contains both input and output parameters.

### Structure Definition

```c
typedef struct {

    BYTE init;
    BYTE counter;
    FLOAT output_freq;
    FLOAT duty_cycle;
    DWORD input_freq;
    WORD load_reg;
    WORD hold_reg;
    BYTE hit_extreme;

} DSCQMM_PWM;
```

### Structure Members

| Name | Description |
| :--- | :--- |
| init | 1 if the current function call is an initializing call, i.e. the first call for this counter and this output frequency. 0 if the current function call is just to modify the duty cycle of a currently-running PWM signal. |
| counter | Counter number: 1-5 for QMM-5, 1-10 for QMM-10 |
| output\_freq | Desired output frequency; the function will select the best clock source from the 9513 chip's built-in frequency generator to achieve the desired output frequency with maximum duty cycle resolution |
| duty\_cycle | Desired duty cycle in percent: range is 0 - 99.99 in steps of .01; a duty cycle of 100% is not possible |
| input\_freq | Input clock source selected by the function |
| load\_reg | Resulting load register value from the selected output frequency and duty cycle |
| hold\_reg | Resulting hold register value from the selected output frequency and duty cycle |
| hit\_extreme | 1 if the function has reached either duty cycle limit \(0 or 99.99\); 0 otherwise |

