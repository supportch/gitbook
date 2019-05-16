# DSCDACS

Structure containing D/A conversion scan settings. This structure is used when performing analog output on several channels simultaneously. One array is filled with data for each channel, and a second array is filled with flags indicating which channels to change. The unselected channels are unchanged.

### Structure Definition

```c
typedef struct {

    BOOL channel_enable[16];
    DSCDACODE* output_codes;
    DSCDACODE DACode[4];
    
} DSCDACS;
```

### Structure Members

| Name | Description |
| :--- | :--- |
| channel\_enable\[16\] | Input Array of flags that selects which analog output channels to change. Select TRUE for each location \(0-15\) for which you want to output new data. |
| output\_codes | Input Array of output codes to send to the corresponding selected channels in channel\_enable\[\]. Locations to use are 0-15. |
| DACode\[4\] | Input Array of output codes to send to the corresponding selected channels in channel\_enable\[\]. Locations to use are 0-3. |

