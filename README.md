# FORK of MPU6050_tockn for faster loading

This library is a fork of nice MPU6050 library from tockn [available here](https://github.com/Tockn/MPU6050_tockn)

The differences between this fork and the original library are at the auto-calibration level (method `calcGyroOffsets()`): the console mode has been removed and the process has been simplified. In arg you can now specify the number of update you want before calibration completion.

This fork was created for my personal use, on a robot plateform. I needed auto-callibration but the startup time was to long while I didn't need a very accurate offset (Gyroscopic position on this robot was only of 1 angle degree in all directions)

## Usage of library 

See [original library](https://github.com/Tockn/MPU6050_tockn)

## Usage of new calibration

```
#include <MPU6050_tockn_fork>
#include <Wire.h>

MPU6050 mpu6050(Wire);

void setup(){
  Wire.begin();
  mpu6050.begin();
  mpu6050.calcGyroOffsets(300); // 300 step of callibration
  // Total loading time should be < 1s on a 16 MIPS MCU
}

```

## Licence
MIT
## Author

Original author : [Tockn](https://github.com/tockn)

Fork : [manuito](https://github.com/manuito)
