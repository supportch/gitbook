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
    BYTE channel; 
    BYTE over_range; 
    BYTE enable;
    
} DSCDASETTINGS;
```

### Structure Members

| Name | Description | Applicable Boards |
| :--- | :--- | :--- |
| polarity | The polarity setting to use for D/A conversions; valid settings are BIPOLAR or UNIPOLAR | Diamond-MM-32DX-AT |
| load\_cal | If TRUE, the board will retrieve the calibration settings for the selected D/A range from the EEPROM and store it in the calibration circuit before performing future D/A conversions. This results in higher accuracy but causes a slight one-time delay of a few milliseconds. If FALSE, the board will use the current calibration settings and start the D/A conversion immediately. Once a particular D/A range's calibration settings are loaded into the board, they will remain loaded until the board powers off or a new set of settings is loaded. | Aries,Ruby-MM-1616 |
| range | Absolute value of maximum voltage. For example, 10.0, or 5.0. Required for DscDACodeToVoltage and DscVoltageToDACode. | Aries,DS-MPE-DAQ0804,Ruby-MM-1616,Zeta,Helix |
| gain | INPUT: 0 = gain of 1, 1 = gain of 2, 2 = gain of 4, 3 = gain of 8 | Diamond-MM-32DX-AT |
| dasim | If set to 1, set the DASIM bit in the DA mode control register. Currently only applies to the Helios SBC. When this bit is set to 1, the DA conversions are kept in the FPGA memory until a trigger is applied to enable the simultaneout output of all the DA channels on the corresponding analong outputs. It is recommended that the DASIM bit be used in the dscDAConvertScan function instead of in the dscDAConvert function. It MUST be noted that this bit is settable only in case of Helios SBC. | DS-MPE-DAQ0804,Zeta,Helix |
| daPolEn | Only applicable to Helios board as of now. If set to 1, the DA polarity is controlled through software. Otherwise the polarity is provided by the hardware jumpers on the board. Thus when set to 1, the software settings override the hardware jumpers. It MUST be noted that this bit is settable only in case of Helios SBC. | Diamond-MM-32DX-AT |
| channel | The variable which stores the D/A channel value | Aries,Ruby-MM-1616 |
| over\_range | To enable/disable the over range | Aries,Ruby-MM-1616 |
| enable | To enable the D/A functionality to perform D/A operation | Aries,Ruby-MM-1616 |

