# DSCQMMSCF

Structure containing configuration data for Special Counter Functions. Refer to the 9513 datasheet for information on special functions.

### Structure Definition

```c
/* QMM special counter actions */

#define QMM_SPECIAL_CLEAR_TOGGLE_OUTPUT 0
#define QMM_SPECIAL_SET_TOGGLE_OUTPUT 1
#define QMM_SPECIAL_STEP_COUNTER 2
#define QMM_SPECIAL_PROGRAM_ALARM 3

typedef struct {

    BYTE counter;
    BYTE action;
    WORD alarm_value;

} DSCQMMSCF;
```

### Structure Members

| Name | Description |
| :--- | :--- |
| counter | Counter no., 1-10 |
| action | Special action for this counter; select from special counter action macros in above list |
| alarm\_value | Alarm value, range 0-65535 Valid only if alarm is enabled \(action = QMM\_SPECIAL\_PROGRAM\_ALARM\) and counter no. is 1, 2, 6, or 7. |

