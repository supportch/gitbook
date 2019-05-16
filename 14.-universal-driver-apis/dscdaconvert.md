# dscDAConvert

```c
BYTE dscDAConvert(DSCB board, BYTE channel, DSCDACODE output_code);
```

Performs a single D/A conversion on the given channel.

{% tabs %}
{% tab title=" Input Parameters" %}
| **Name** | **Description** |
| :--- | :--- |
| DSCB  | The handle of the board to operate on |
| channel | Selected output channel for the D/A conversion |
| DSCDACODE  | Output code representing the desired output voltage. See the board's user manual for information on the translation between output voltage and output code. The range of output code for 12 bit DACs is 0 ~ 4095. The range of output code for 16 bit DACs is 0 ~ 65535. |
{% endtab %}
{% endtabs %}

| Return Value |
| :--- |
| Error code or 0. |

