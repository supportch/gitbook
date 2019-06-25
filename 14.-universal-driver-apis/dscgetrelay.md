# dscGetRelay

```c
BYTE dscGetRelay(DSCB board, BYTE relay, BYTE* value);
```

Gets the state of one relay on the board.

{% tabs %}
{% tab title="Input Parameters" %}
| Name | Description |
| :--- | :--- |
| DSCB | The handle of the board to operate on |
| relay | Selected relay |
| value | Current relay state \(0 or 1\). Please consult the user manual for your particular product to determine the relationship between the value and the relay state |
{% endtab %}
{% endtabs %}

| Return Value |
| :--- |
| Error code or 0. |

