# Blue pill

Playing around with Rust embedded systems.

## Commands

```
openocd -f interface/stlink-v2.cfg -f target/stm32f1x.cfg
```

When I run:

```
st-flash read ./saved.img 0x80000000 0x1000
hexedit saved.img
```

I see mostly `0xFF`, some `80 00` and `40 00`. Sems off.
