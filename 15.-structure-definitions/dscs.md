# DSCS

Structure containing interrupt operation status information. Used by dscGetStatus\(\).

### Structure Definition

```c
typedef struct { 

    BYTE op_type; 
    DWORD transfers; 
    DWORD total_transfers; 
    DWORD da_transfers; 
    DWORD overflows; 
    
    } DSCS;
```

### Structure Members

| Name | Description | Applicable Boards |
| :--- | :--- | :--- |
| op\_type | The current operation type, either OPTYPE\_NONE or any bit-wise combination of INT\_TYPE\* currently running | Diamond-MM-16-AT,Diamond-MM-16RP-AT,Diamond-MM-32DX-AT,Diamond-MM-32X-AT,Diamond-MM-AT |
| transfers | The number of A/D transfers that have taken place for the current cycle \(identical to total\_transfers in non-cycle mode.\) | Diamond-MM-16-AT,Diamond-MM-16RP-AT,Diamond-MM-32DX-AT,Diamond-MM-32X-AT,Diamond-MM-AT |
| total\_transfers | The total number of A/D conversions that have taken place since the interrupt operation began. When scans are occurring, this variable increments by the scan size. | Diamond-MM-16-AT,Diamond-MM-16RP-AT,Diamond-MM-32DX-AT,Diamond-MM-32X-AT,Diamond-MM-AT |
| da\_transfers | Similar to transfers but for D/A conversions. | Diamond-MM-16-AT,Diamond-MM-32DX-AT,Diamond-MM-32X-AT,Diamond-MM-AT |
| overflows | On boards with FIFOs \(AT boards and Prometheus\), this parameter indicates the number of times the FIFO overflowed during an A/D interrupt operation. During correct operation, this number should always be zero. If it ever becomes nonzero, it means that some A/D data was missed, because the A/D FIFO reached its limit before the interrupt routine could read data out. When the FIFO becomes full, it will not accept any more data, although the board continues to take samples. Once the interrupt routine reads data from the FIFO, it will resume storing A/D data. This value is reset to zero each time an interrupt operation starts. This parameter can be used to verify that A/D data was acquired accurately with no missing samples. It can also be used to search for the maximum sampling rate achievable on your computer for the given settings. | Diamond-MM-16-AT,Diamond-MM-16RP-AT,Diamond-MM-32DX-AT,Diamond-MM-32X-AT,Diamond-MM-AT |



