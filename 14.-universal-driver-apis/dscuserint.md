# dscUserInt

```c
BYTE dscUserInt(DSCB board, DSCUSERINT* dscuserint, DSCUserInterruptFunction func);
```

Starts execution of a user interrupt function alone \(without another driver interrupt function\).

{% tabs %}
{% tab title=" Input Parameters" %}
| **Name** | **Description** |
| :--- | :--- |
| board | The handle of the board to operate on |
| dscuserint | Structure containing configuration information for the user interrupt operation |
| func | The name of the user interrupt function |
{% endtab %}
{% endtabs %}

| Return Value |
| :--- |
| Error code or 0. |

