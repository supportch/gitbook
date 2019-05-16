# DSCEMMDIORESETINT

Structure used to reset Emerald-MM-DIO user interrupts and edge detection activity.

### Structure Definition

```c
typedef struct {

    BOOL use_lock_port;
    BOOL lock_port[6];
    BYTE edge_detect_clear[3];

} DSCEMMDIORESETINT;
```

### Structure Members

| Name | Description |
| :--- | :--- |
| use\_lock\_port | 0 = ignore lock\_port values below; 1 = use lock\_port values below |
| lock\_port\[6\] | Values for the port lock control bits. A 1 for any port prevents that port's output registers from being changed, while a 0 pemits them to be changed. See the Emerald-MM-DIO user manual for more details. |
| edge\_detect\_clear\[3\] | A 1 for any port will clear that port's edge detect registers; a 0 will leave the edge detect registers unchanged. |

