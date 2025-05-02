# zephyr_hm01b0

Example of porting hm01b0 library to Zephyr RTOS.

Original example is at : https://www.raspberrypi.com/news/real-time-monochrome-camera-input-on-raspberry-pi-pico/

The line below must be modified in hardware/i2c.h in pico_sdk. The () after PICO_DEFAULT_I2C_INSTANCE should be removed

```
#define PICO_DEFAULT_I2C_INSTANCE() (__CONCAT(i2c,PICO_DEFAULT_I2C))
```