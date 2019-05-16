# DSCADSETTINGS

### Structure Definition

```c
typedef struct {

    BYTE current_channel;
    BYTE gain;
    BYTE range;
    BYTE polarity;
    BYTE load_cal;
    BYTE scan_interval;
    BYTE addiff;
    BYTE clk;
    BOOL gainTableE;
    BOOL gateE;
    BOOL turbo;
    BYTE low_channel;
    BYTE high_channel;
    BYTE prog_delay;
    BOOL Sedi;
    BOOL Sign;
    BOOL ScanEnable;
    BOOL ProgInt;
    
} DSCADSETTINGS;
```

### Structure Members

<table>
  <thead>
    <tr>
      <th style="text-align:left">Name</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">current_channel</td>
      <td style="text-align:left">The channel on which to perform A/D conversions</td>
    </tr>
    <tr>
      <td style="text-align:left">Gain</td>
      <td style="text-align:left">The gain setting to use for A/D conversions; valid settings are GAIN_1,
        GAIN_2, GAIN_4, and GAIN_8</td>
    </tr>
    <tr>
      <td style="text-align:left">range</td>
      <td style="text-align:left">The range setting for A/D conversions; this is not to be confused with
        the term &quot;A/D range&quot; or &quot;input range&quot;. Valid settings
        are RANGE_5 or RANGE_10</td>
    </tr>
    <tr>
      <td style="text-align:left">polarity</td>
      <td style="text-align:left">The polarity setting to use for A/D conversions; valid settings are BIPOLAR
        or UNIPOLAR</td>
    </tr>
    <tr>
      <td style="text-align:left">load_cal</td>
      <td style="text-align:left">If TRUE, the board will retrieve the calibration settings for the selected
        A/D range from the EEPROM and store it in the calibration circuit before
        performing the A/D conversion. This results in higher accuracy but causes
        a slight delay of a few milliseconds. If FALSE, the board will use the
        current calibration settings and start the A/D conversion immediately.
        Once a particular A/D range&apos;s calibration settings are loaded into
        the board, they will remain loaded until the board powers off or a new
        set of settings is loaded. When the board powers up, it automatically loads
        the settings defined as the boot mode. The boot mode is set with the autocal
        function.</td>
    </tr>
    <tr>
      <td style="text-align:left">scan_interval</td>
      <td style="text-align:left">
        <p>Determines the time delay between consecutive A/D conversions during an
          A/D scan operation. When you perform an A/D scan, the individual A/D samples
          will be spaced apart by exactly this amount of time. The time delay affects
          the maximum possible sample rate. For example, if you want to achieve a
          100KHz sample rate, the maximum scan interval is 1/100KHz = 10 microseconds.</p>
        <p>0 20 microseconds (default value)</p>
        <p>1 15 microseconds</p>
        <p>2 10 microseconds</p>
        <p>3 5 microseconds</p>
        <p>4 9 microseconds</p>
        <p>5 4 microseconds</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">addif</td>
      <td style="text-align:left">For Hercules and Elektra only, 0 = SINGLE_ENDED or 1 = DIFFERENTIAL</td>
    </tr>
    <tr>
      <td style="text-align:left">clk</td>
      <td style="text-align:left">Clock INPUT: 0 = ADSTART=1, 1 = falling edge of P_ADTRIG, 2 = rising edge
        of conter0, 3 = rising edge of counter1</td>
    </tr>
    <tr>
      <td style="text-align:left">gainTableE</td>
      <td style="text-align:left">INPUT: TRUE = sets RTEN=1, FALSE = sets RTEN=0 RTEN tells FPGA to load
        gain table from internal memory</td>
    </tr>
    <tr>
      <td style="text-align:left">gateE</td>
      <td style="text-align:left">INPUT: TRUE = set A/D gate enable, FALSE = disables A/D gate enable</td>
    </tr>
    <tr>
      <td style="text-align:left">turbo</td>
      <td style="text-align:left">INPUT: TRUE = sets A/D turbo feature, FALSE = disables A/D turbo</td>
    </tr>
    <tr>
      <td style="text-align:left">low_channel</td>
      <td style="text-align:left">low channel for A/D conversion</td>
    </tr>
    <tr>
      <td style="text-align:left">low channel for A/D conversion</td>
      <td style="text-align:left">high channel for A/D conversion</td>
    </tr>
    <tr>
      <td style="text-align:left">prog_delay</td>
      <td style="text-align:left">8-bit programmable scan delay</td>
    </tr>
    <tr>
      <td style="text-align:left">Sedi</td>
      <td style="text-align:left">0 = single-ended, 1 = differential</td>
    </tr>
    <tr>
      <td style="text-align:left">Sign</td>
      <td style="text-align:left">if Differential mode is enabled: 0 = even channel is high; 1 = odd channel
        is high</td>
    </tr>
    <tr>
      <td style="text-align:left">ScanEnable</td>
      <td style="text-align:left">0 = disable, 1 = enable</td>
    </tr>
    <tr>
      <td style="text-align:left">ProgInt</td>
      <td style="text-align:left">If ScanInterval is programmable, then ProgInt is the time in nano seconds
        (0 &#x2013; 255)</td>
    </tr>
  </tbody>
</table>