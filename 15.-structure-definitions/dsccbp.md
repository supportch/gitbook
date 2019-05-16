# DSCCBP

Structure containing hardware settings for the current board. Some elements are unique to particular boards.

### Structure Definition

```c
typedef struct { 

    BYTE boardtype; 
    DSCB boardnum; 
    DWORD phys_mem_address[PCI_MAX_RESOURCES]; 
    DWORD user_mem_address[PCI_MAX_RESOURCES]; 
    DWORD io_address[PCI_MAX_RESOURCES]; 
    DWORD irq_level[PCI_MAX_RESOURCES]; 
    BYTE pci_slot; 
    WORD pci_devid; 
    WORD pci_vendorid; 
    BYTE bytBAR; 
    BOOL FPGAIDMajor; 
    BOOL FPGAIDMinor; 
    BOOL FPGARevMajor; 
    BOOL FPGARevMinor; 
    BOOL BoardIDMajor; 
    BOOL BoardIDMinor; 
    BOOL BoardRevMajor; 
    BOOL BoardRevMinor; 
    
    } DSCCBP;
```

### Structure Members

| Name | Description |
| :--- | :--- |
| boardtype | The board type constant; automatically filled by dscPCIInitBoard; |
| boardnum | The handle to the board; automatically filled in by dscPCIInitBoard |
| phys\_mem\_address | Physical memory address assigned to board |
| user\_mem\_address | User-space memory address assigned to board |
| io\_address | I/O address assigned to board |
| irq\_level | IRQ levels assigned to the board |
| pci\_slot | PCI slot jumper configured on the board |
| pci\_devid | PCI device ID for the board |
| pci\_vendorid | PCI vendor ID for the board |
| bytBAR | BAR to use for I/O |
| FPGAIDMajor | FPGA ID major value |
| FPGAIDMinor | FPGA ID minor value |
| FPGARevMajor | FPGA Revision major value |
| FPGARevMinor | FPGA Revision minor value |
| BoardIDMajor | Board ID major value |
| BoardIDMinor | Board ID minor value |
| BoardRevMajor | Board Revision major value |
| BoardRevMinor | Board Revision minor value |

