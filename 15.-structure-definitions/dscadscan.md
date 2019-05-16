# DSCADSCAN

### Structure Definition

```c
typedef struct {

    BYTE low_channel;
    BYTE high_channel;
    DSCSAMPLE* sample_values;
    BYTE gain;
    BOOL ScanEnable;
    BOOL ScanInterval;
    BOOL ProgInt;

} DSCADSCAN;
```

### Structure Members

| Name | Description |
| :--- | :--- |
| low\_channel | The starting channel in the scan range on which to perform A/D conversions |
| high\_channel | The ending channel in the scan range on which to perform A/D conversions; must be greater than or equal to low\_channel. |
| sample\_values | Pointer to a buffer to hold the results of the A/D conversions |
| Gain | Gain setting for A/D conversions; valid settings are GAIN\_1, GAIN\_2, GAIN\_4, or GAIN\_8 |
| ScanEnable | To enable or disable the scan operation |
| ScanInterval | The time gap between each A/D scan |
| ProgInt | If ScanInterval is programmable, then ProgInt is the time in nano seconds |

