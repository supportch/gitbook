# DSCWGCONFIG

Structure containing D/A wave form parameters for function DscWGConfigSet\(\).

### Structure Definition

```c
#define WG_SRC_MANUAL 0
#define WG_SRC_CTR0 1
#define WG_SRC_CTR12 2
#define WG_SRC_EXT 3
#define WG_CH_PER_FRAME_1 0
#define WG_CH_PER_FRAME_2 1
#define WG_CH_PER_FRAME_4 2

typedef struct
{

    DWORD depth;
    DWORD ch_per_frame;
    DWORD source;
    BYTE cycle;
    DWORD *Waveform;
    BOOL Frames;
    BOOL FrameSize;
    BOOL *Channels;
    BOOL Clock;
    FLOAT Rate;

} DSCWGCONFIG;
```

### Structure Members

| Name | Description |
| :--- | :--- |
| depth | WG total D/A sample size \(absolute, 64, 128, 256, 512, and 1024\) |
| ch\_per\_frame | Number of values to output from the buffer per frame/trigger, check define WG\_CH\_PER\_FRAME\_XXX |
| source | WG trigger source, check define WG\_SRC\_XXX |
| cycle | If cycle = 1, waveform restarts, otherwise runs only once - RMM-1616 only |
| Waveform | pointer to array of 16-bit unsigned data; If multiple channels are being set up at the same time, the data must be previously interleaved by the program, i.e. ch. 0, ch. 1, ch. 2, ch. 0, ch. 1, ch. 2, \85; the array size must be equal to Frames x FrameSize; the array size must be no greater than 2048 |
| Frames | Total number of frames in the array |
| FrameSize | Number of channels to be driven = frame size |
| Channels | List of channels to be driven by the waveform generator, the number of values in this array must be equal to FrameSize and channels can be in any sequence |
| Clock | To select the clock source, 0 = software increment; 1 = counter/timer 0 output; 2 = counter/timer 1 output; 3 = DIO pin D0 |
| Rate | frame update rate, Hz \(only used if Clock = 1 or 2\) |

