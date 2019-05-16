# DSCOPTOSTATE

Structure containing information on the current optoinput state of the board. For use with the dscOptoGetState and dscOptoSetState functions.

### Structure Definition

```c
#define DSCUD_MAX_OPTO 8

typedef struct {

    BYTE edge_polarity[DSCUD_MAX_OPTO];
    BYTE edge_detect_enab[DSCUD_MAX_OPTO];
    BYTE edge_status[DSCUD_MAX_OPTO];
    BYTE oint_state[DSCUD_MAX_OPTO];
    BYTE dmm48at_oint_state;

} DSCOPTOSTATE;
```

### Structure Members

| Name | Description |
| :--- | :--- |
| edge\_polarity | Polarity state of each optoinput |
| edge\_detect\_enab | Edge detect enable state of each optoinput 0 = disabled, 1 = enabled |
| edge\_status | Edge detect status for each optoinput. 0 = no edge detected since last check 1 = edge detected since last check |
| oint\_state | Optoinput state \(depends on polarity for boards which support this feature.\) |
| dmm48at\_oint\_state | When using opto edges to drive interrupts on the Diamond-MM-48-AT, the edge registers must be read \(and subsequently reset\) by the kernel interrupt handler before the user has a chance to read them back. The kernel interrupt handler will save the opto state register in this location so that the user can see which edge triggered the interrupt inside of the user interrupt function. |

