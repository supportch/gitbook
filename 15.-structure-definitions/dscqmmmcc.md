# DSCQMMMCC

Structure containing configuration data for Multiple Counter Control. This structure is used to execute load, arm, disarm, and save actions. An Arm command causes the counter to start counting, and a Disarm command causes it to stop. The counter will not count until it receives an Arm command. The Save command or Disarm and Save command are used to latch the current contents of the counter into the Hold register for reading. If just the Save command is executed, the counter will continue to count; this is equivalent to the Lap button on a stopwatch. After executing one of these commands, use the dscReadHoldRegister function to read the latched data. The Load command or Load and Arm command are used to load the contents of the Load register into the counter before or while arming it. Before executing one of these commands, use the dscSetLoadRegister\(\) function to load the Load register with the desired data. If you are using a QMM-5 board with only one 9513 chip, or if you are acting on only one counter chip, set the other counter's action to QMM\_ACTION\_NONE \(0\).

### Structure Definition

```c
typedef struct {

    BYTE group1_action;
    BYTE group1_counter_select;
    BYTE group2_action;
    BYTE group2_counter_select;

} DSCQMMMCC;
```

### Structure Members

| Name | Name |
| :--- | :--- |
| group1\_action | Determines the action for counter group 1 \(counters 1-5\); select from counter action macros in above list |
| group1\_counter\_select | Selects which counters will be acted on by the action in group1\_action. All counters in the group are acted on in the same way at the same time. |
| group2\_action | Determines the action for counter group 2 \(counters 6-10\) |
| group2\_counter\_select | Selects which counters will be acted on by the action in group2\_action All counters selected in each group receive the same action specified for that group. The parameters for group1\_counter\_select and group2\_counter\_select use the following format: Group1\_counter\_select: Bit No. 7 6 5 4 3 2 1 0 Name 0 0 0 CTR5 CTR4 CTR3 CTR2 CTR1 Group2\_counter\_select: Bit No. 7 6 5 4 3 2 1 0 Name 0 0 0 CTR10 CTR9 CTR8 CTR7 CTR6 CTRn select counter n; 1 = selected, 0 = not selected |

