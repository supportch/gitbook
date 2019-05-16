# DSCCS

Structure containing individual counter information. This is used for functions operating on 82C54 counters \(all boards except Quartz-MM\).

### Structure Definition

```c
typedef struct {

    DWORD value;
    BYTE status;

} DSCCS;
```

### Structure Members

| Name | Description |
| :--- | :--- |
| value | The counter read-back value |
| status | Counter read-back status |

