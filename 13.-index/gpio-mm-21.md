# GPIO-MM-21

### Board Initialization

To use the GPIO-MM-21 board in UD, the dscInitBoard function should use the board macro DSC\_GPIO21. This is shown in the example below.

```c
dscInitBoard( DSC_GPIO21 , &dsccb, &board );
```

### Digital I/O

<table>
  <thead>
    <tr>
      <th style="text-align:left"></th>
      <th style="text-align:left"></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Max Ports:</td>
      <td style="text-align:left">
        <p>12 8-bit bi-directional ports with programmable direction bit by bit and
          inverting logic thus providing 96 DIO lines.</p>
        <p>Digital I/O lines on GPIO-MM-21 do not require configuration. Writing
          a 0 to any bit drives the pin high and also enables it as an input. Writing
          a 1 to a bit drives the pin low and forces it to an output. A high input
          will read back as a 0, and a low input will readback as a 1.</p>
      </td>
    </tr>
  </tbody>
</table>### GPIO-MM-21 Universal Driver Functions

* dscDIOInputBit\(\) 
* dscDIOInputByte\(\) 
* dscDIOOutputBit\(\) 
* dscDIOOutputByte\(\) 
* dscDIOSetConfig\(\)

