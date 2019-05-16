# DSCDASETTINGS

Structure containing current D/A conversion settings.

### Structure Definition

```c
typedef struct { 

    BYTE polarity; 
    BYTE load_cal; 
    FLOAT range; 
    BYTE gain; // New for the Helios and later D/A-capable boards. 
    BYTE dasim ; /* DASIM bit for simultaneous update*/ 
    BYTE daPolEn ; /* 1 = Polarity from SW, 0 = polarity by HW jumpers.*/ 
    BYTE daUR ; /* DA Unique Range. 1 will setup range settings for the CH*/ 
    BYTE daURChannel ;/* Unique range settings for the channel.Ignored if daUR is 0*/ 
    BYTE channel; 
    BYTE over_range; 
    BYTE enable;
    
} DSCDASETTINGS;
```

### Structure Members

| Name | Description |
| :--- | :--- |
| polarity | The polarity setting to use for D/A conversions; valid settings are BIPOLAR or UNIPOLAR |
| range | Absolute value of maximum voltage. For example, 10.0, or 5.0. Required for DscDACodeToVoltage and DscVoltageToDACode. |
| load\_cal | If TRUE, the board will retrieve the calibration settings for the selected D/A range from the EEPROM and store it in the calibration circuit before performing future D/A conversions. This results in higher accuracy but causes a slight one-time delay of a few milliseconds. If FALSE, the board will use the current calibration settings and start the D/A conversion immediately. Once a particular D/A range's calibration settings are loaded into the board, they will remain loaded until the board powers off or a new set of settings is loaded. |
| dasim | If set to 1, set the DASIM bit in the DA mode control register. Currently only applies to the Helios SBC. When this bit is set to 1, the DA conversions are kept in the FPGA memory until a trigger is applied to enable the simultaneout output of all the DA channels on the corresponding analong outputs. It is recommended that the DASIM bit be used in the dscDAConvertScan function instead of in the dscDAConvert function. It MUST be noted that this bit is settable only in case of Helios SBC. |
| daPolEn | Only applicable to Helios board as of now. If set to 1, the DA polarity is controlled through software. Otherwise the polarity is provided by the hardware jumpers on the board. Thus when set to 1, the software settings override the hardware jumpers. It MUST be noted that this bit is settable only in case of Helios SBC. |
| daUR | When this field of the structure is set to 1, the Helios board will set the channel in the next field to have a unique range setting independent of the other 3 channels. It must be noted that if every channel is intended to be set to separate ranges, the dscDASetSettings function must be called 4 times and for every instance the daUR field needs to be set to 1. |
| daURChannel | The channel which gets the individual unique range setting. This channel number is different from the channel number for performing the actual DA conversion. This channel number is applicable only if the daUR is set to 1. If daUR is set to 0, the daURChannel value is ignored by the Helios board. |
| gain | INPUT: 0 = gain of 1, 1 = gain of 2, 2 = gain of 4, 3 = gain of 8 |
| channel | The variable which stores the D/A channel value |
| over\_range | To enable/disable the over range |
| enable | To enable the D/A functionality to perform D/A operation |

