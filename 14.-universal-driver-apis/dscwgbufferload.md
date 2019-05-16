# dscWGBufferLoad

```c
BYTE dscWGBufferLoad(DSCB board, DSCWGCONFIG* config)
```

Configures D/A waveform by copying the waveform data to the board waveform buffer and programming the number of frames into the board.

{% tabs %}
{% tab title="Input Parameters" %}
| **Name** | **Description** |
| :--- | :--- |
| board | The handle of the board to operate on |
| config | Structure containing configuration information for D/A wave form generator |
{% endtab %}
{% endtabs %}

| Return Value |
| :--- |
| Error code or 0. |

