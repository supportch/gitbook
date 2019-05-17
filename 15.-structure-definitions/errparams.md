# ERRPARAMS

Structure containing error code information resulting from a Universal Driver function call. An error code is generated as the return value by each driver function.

### Structure Definition 



```c
typedef struct {

    BYTE errcode;
    char* errstring;

} ERRPARAMS;
```

### Structure Members

| Name | Description |
| :--- | :--- |
| errcode | The error code representing the particular error |
| errstring | The string description corresponding to the error code in ErrCode |

