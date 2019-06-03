# DSCSPECIALFUNC

Structure containing information on all special functions. This is used for functions operating in DSC\_MPEGPIO.

### Structure Definition

```c
typedef struct {

    BYTE cmd;
    BOOL *Data;
    BOOL Config;

} DSCSPECIALFUNC;
```

### Structure Members

| Name | Description | Applicable Boards |
| :--- | :--- | :--- |
| cmd | Command provided from the user | Aries |
| Data | To read the data from the device | Aries |
| Config | Pull Up/Down configuration value | DS-MPE-GPIO |

