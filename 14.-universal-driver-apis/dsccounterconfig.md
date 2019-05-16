# dscCounterConfig

```c
BYTE dscCounterConfig(DSCB board, DSCCR* dsccr);
```

This function configures the counter for up and down direction, loads data, registers the clock source, Reload the counter. Configures the counter for its respective operation.

{% tabs %}
{% tab title=" Input Parameters" %}
| **Name** | **Description** |
| :--- | :--- |
| board | The handle of the board to operate on |
| dsccr | The settings for all counters in the structure dsccr; see DSCCR definition |
{% endtab %}
{% endtabs %}

| Return Value |
| :--- |
| Error code or 0. |

