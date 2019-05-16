# DSCADCALPARAMS

Structure containing A/D auto-calibration settings. Used by dscADAutocal\(\).

### Structure Definition

```c
typedef struct { 

    BYTE adrange; 
    BYTE boot_adrange; 
    FLOAT ad_offset; 
    FLOAT ad_gain; 
    BOOL use_eeprom; 
    BYTE calmux_output; 
    DFLOAT offset; 
    DFLOAT gain; 
    int Range; 
    int BootSet; 
    float *OffsetErrors ; 
    float *FullScaleErrors; 
    int Express; 
    float Tolerance; 
    int Result; 
    
    } DSCADCALPARAMS;
```

### Structure Members

| Name | Description |
| :--- | :--- |
| adrange | A/D range to calibrate; if adrange = 255, then all A/D ranges will be calibrated |
| boot\_adrange | A/D range whose calibration settings will be loaded from the EEPROM when the board is first powered on. |
| ad\_offset | The maximum offset error in A/D LSBs resulting from the autocalibration process |
| ad\_gain | The maximum gain error in A/D LSBs resulting from the autocalibration process |
| use\_eeprom | To set the reference values, use dsc\(S/G\)etReferenceVoltages |
| calmux\_output | Bits\[2-0\] - channel selection, Bits\[4-3\] - calmux reference selection, Bit\[5\] - use all modes from table, Bit\[6\] - use all calmux output voltages Bit\[7\] - override bit set to high to use settings for Bits\[6-0\] |
| offset | Differences between target and measured values in volts |
| gain | Differences between target and measured values in volts |
| Range | 0-7 for single range or -1 for all ranges |
| BootSet | 0 = don’t set boot range, 1 = set boot range |
| OffsetErrors | Array of offset error values \(low end of scale\) resulting from calibration procedure. |
| FullScaleErrors | array of full-scale error values resulting from calibration procedure |
| Express | 0 = run full calibration procedure, 1 = enable express mode |
| Tolerance | 0 = use driver default error tolerance, nonzero means use given tolerance |
| Result | 0 = failure, 1 = success |

