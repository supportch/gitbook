# DSCS

Structure containing interrupt operation status information. Used by dscGetStatus\(\).

### Structure Definition

```c
typedef struct { 

    BYTE op_type; 
    DWORD transfers; 
    DWORD total_transfers; 
    DWORD da_transfers; 
    DWORD da_total_transfers; 
    DWORD overflows; 
    
    } DSCS;
```

### Structure Members

| Name | Description |
| :--- | :--- |
| op\_type | The current operation type, either OPTYPE\_NONE or any bit-wise combination of INT\_TYPE\* currently running |
| transfers | The number of A/D transfers that have taken place for the current cycle \(identical to total\_transfers in non-cycle mode.\) |
| total\_transfers | The total number of A/D conversions that have taken place since the interrupt operation began. When scans are occurring, this variable increments by the scan size. |
| da\_transfers | Similar to transfers but for D/A conversions. |
| da\_total\_transfers | Similar to total\_transfers but for D/A conversions. |
| overflows | On boards with FIFOs \(AT boards and Prometheus\), this parameter indicates the number of times the FIFO overflowed during an A/D interrupt operation. During correct operation, this number should always be zero. If it ever becomes nonzero, it means that some A/D data was missed, because the A/D FIFO reached its limit before the interrupt routine could read data out. When the FIFO becomes full, it will not accept any more data, although the board continues to take samples. Once the interrupt routine reads data from the FIFO, it will resume storing A/D data. This value is reset to zero each time an interrupt operation starts. This parameter can be used to verify that A/D data was acquired accurately with no missing samples. It can also be used to search for the maximum sampling rate achievable on your computer for the given settings. |



