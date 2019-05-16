# dscUserIntRun

```c
BYTE dscUserIntRun(DSCB board, DSCUSERINT* dscuserint);
```

This function is used to start user interrupts when they are running in Alone mode.

{% tabs %}
{% tab title=" Input Parameters" %}
| **Name** | **Description** |
| :--- | :--- |
| board | The handle of the board to operate on |
| dscuserint | Structure containing configuration information for the user interrupt operation |
{% endtab %}
{% endtabs %}

| Return Value |
| :--- |
| Error code or 0. |

