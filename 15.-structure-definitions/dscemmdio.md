# DSCEMMDIO

Structure to define the current configuration of an Emerald-MM-DIO board. This structure is used both as an input, to define the board's state, and as an output, to inquire about the board's state.

### Structure Definition

```c
typedef struct {

    BYTE DIOpins[6];
    BOOL lock_port[6];
    BYTE edge_polarity[3];
    BYTE edge_detect[3];
    BYTE edge_detect_clear[3];
    BYTE edge_detect_int[3];
    BOOL use_DIOpins;
    BOOL use_lock_port;
    BOOL use_edge_polarity;
    BOOL use_edge_detect;
    BYTE interrupt_status;

} DSCEMMDIO;
```

### Structure Members

| Name | Description |
| :--- | :--- |
| DIOpins\[6\] | The values to write to the DIO pins, or values read from DIO pins. |
| lock\_port\[6\] | Values for the port lock control bits. A1 for any port prevents that port's output registers from being changed, while a 0 pemits them to be changed. See the Emerald-MM-DIO user manual for more details. |
| edge\_polarity\[3\] | Three 8-bit values to determine the polarity of each pin on ports 0 through 2. Each BYTE represents one port with 8 pins: 0 = negative edge and 1 = positive edge for each bit in that port. Each bit of these three bytes determines the polarity of the corresponding I/O bit. |
| edge\_detect\[3\] | 3 byte values of either 0 or 1, corresponding to ports 0 - 2. A 1 for any port will enable edge detection for the entire port; a 0 will disable edge detection for the entire port. |
| edge\_detect\_clear\[3\] | 3 byte values of either 0 or 1, corresponding to ports 0 - 2. A 1 for any port will clear that port's 8 edge detect registers; a 0 will leave the 8 edge detect registers unchanged. |
| edge\_detect\_int\[3\] | Read-only values specifying if an edge was detected on the pin since its port was last cleared. Each bit of each element corresponds to a digital input line on ports 0-2. |
| use\_DIOpins | 0 = ignore DIOpins\[ \] array, 1 = use DIOpins\[ \] array |
| use\_lock\_port | 0 = ignore lock\_port\[ \] array, 1 = use lock\_port\[ \] array |
| use\_edge\_polarity | 0 = ignore edge\_polarity\[ \] array, 1 = use edge\_polarity\[ \] array |
| use\_edge\_detect | 0 = ignore edge\_detect\[ \] array, 1= use edge\_detect\[ \] array |
| interrupt\_status | Read-only value indicating the interrupt request status of ports 0-2; bits 2-0 are the status for interrupt requests 2-0, respectively; 1 = interrupt pending / edge detected; 0 = no interrupt pending / no edge detected |

