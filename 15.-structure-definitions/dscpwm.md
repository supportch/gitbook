# DSCPWM

Structure containing pulse width modulation parameters for DscPWMFunction\(\).

### Structure Definition

```c
typedef struct {

    DFLOAT output_freq;
    FLOAT duty_cycle;
    BYTE polarity;
    BYTE pwm_circuit;
    BOOL output_enab;
    BYTE pwm_command;
    BYTE run;
    BOOL Divisor;
    BOOL CmdData;

} DSCPWM;
```

### Structure Members

| Name | Description |
| :--- | :--- |
| output\_freq | Output frequency of the PWM signal \(i.e. frequency of subsequent duty cycles.\) |
| duty\_cycle | Percentage of time that the signal will be in the active state. Valid duty cycles range from 0.0 to 100.0. |
| polarity | Determines the active state of the PWM signal \(for boards that support this.\) 0 = high, 1 = low |
| pwm\_circuit | Which PWM circuit this function should configure. Depending on the board this will represent either physical or logical counters. |
| output\_enab | Enable signal output. 1 = enable, 0 = disable |
| pwm\_command | PWM Command to send to the pwm\_circuit |
| run | To initiate and run the PWM |
| Divisor | 24-bit value for use with period and duty cycle commands |
| CmdData | auxiliary PWM command data |

