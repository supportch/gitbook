# dscADAutoCal

```c
BYTE dscADAutoCal(DSCB board, DSCADCALPARAMS* params)
```

Performs an A/D auto-calibration on a selected A/D range or on all A/D ranges. Valid settings for params-&gt;adrange are 0-15 for an individual range or 255 for all ranges. See the board-specific information in Chapter 10 for descriptions of the valid ranges for each A/D board. This function incurs a delay of 0.5 - 2 seconds per A/D range to perform the auto-calibration process.

{% tabs %}
{% tab title=" Input Parameters" %}
| **Name** | **Description** |
| :--- | :--- |
|  DSCB | The handle of the board to operate on |
| [DSCADCALPARAMS](../15.-structure-definitions/dscadcalparams.md) | The A/D calibration settings to be used in the auto-calibration process. See the definition of DSCADCALPARAMS. |
{% endtab %}
{% endtabs %}

| Return Value |
| :--- |
| Error code or 0. |



