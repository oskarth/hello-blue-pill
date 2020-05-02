# Blue pill

Playing around with Rust embedded systems.

## Commands

```
openocd -f interface/stlink-v2.cfg -f target/stm32f1x.cfg
```

When I run:

```
st-flash read ./saved.img 0x8000000 0x1000
hexedit saved.img
```

I see mostly `0xFF`, some `80 00` and `40 00`. Sems off.

```
> st-flash write ./saved.img 0x8000000
st-flash 1.5.1
2020-05-02T13:31:44 INFO common.c: Loading device parameters....
2020-05-02T13:31:44 INFO common.c: Device connected is: F1 Medium-density device, id 0x20036410
2020-05-02T13:31:44 INFO common.c: SRAM size: 0x5000 bytes (20 KiB), Flash: 0x10000 bytes (64 KiB) in pages of 1024 bytes
2020-05-02T13:31:44 INFO common.c: Ignoring 4096 bytes of 0xff at end of file
2020-05-02T13:31:44 INFO common.c: Attempting to write 4096 (0x1000) bytes to stm32 address: 134217728 (0x8000000)
Flash page at addr: 0x08000c00 erased
2020-05-02T13:31:44 INFO common.c: Finished erasing 4 pages of 1024 (0x400) bytes
```

Hmm

`st-flash erase` doesn't lead to deice stopping to blink.
