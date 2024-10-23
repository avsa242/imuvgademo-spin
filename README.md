# imu-demo-vga
--------------

This is a P2X8C4M64P/Propeller 2 demo application that displays live data from an IMU in a graphical representation (e.g., orientation, movement rate, etc)

**IMPORTANT**: This software is meant to be used with the ~~[spin-standard-library](https://github.com/avsa242/spin-standard-library) (P8X32A) or~~ [p2-spin-standard-library](https://github.com/avsa242/p2-spin-standard-library) (P2X8C4M64P). Please install the applicable library first before attempting to use this code, otherwise you will be missing several files required to build the project.


## Videos

* [LSM9DS1 Gyro](https://youtu.be/nFppKTgk1ds)
* [MPU9250 Gyro](https://youtu.be/OZ-gQdGFW-k)
* [MPU9250 Accel](https://youtu.be/X_TVRA0FTkQ)


## Salient Features

* `accel_ray()`: Displays 3DoF accelerometer data as rays radiating from the screen center outwards in proportion with acceleration experienced by each axis (currently static orientation)
* `gyro_ray()`: Display 3DoF gyroscope data as above, but in a pseudo-3D fashion. Trig is used to locate the endpoints of the lines following an elliptical path around the center of the screen, with a circle also attached to the endpoint. The circle radius changes with movement to give a slight sense of depth.
* `mag_plot()`: Display 3DoF magnetometer data plotted in x, y as three functions: XY, XZ, YZ


## Requirements

P2/SPIN2:
* p2-spin-standard-library
* VGA display (Parallax A/V accessory board #64006-ES or equivalent)

Supported IMUs:
* MPU9250 (I2C)
* LSM9DS1 (I2C, SPI)


## Compiler Compatibility

| Processor | Language | Compiler               | Backend      | Status                |
|-----------|----------|------------------------|--------------|-----------------------|
| P1        | SPIN1    | FlexSpin (6.9.4)       | Bytecode     | Not implemented       |
| P1        | SPIN1    | FlexSpin (6.9.4)       | Native/PASM  | Not implemented       |
| P2        | SPIN2    | FlexSpin (6.9.4)       | NuCode       | Untested              |
| P2        | SPIN2    | FlexSpin (6.9.4)       | Native/PASM2 | OK                    |

(other versions or toolchains not listed are __not supported__, and _may or may not_ work)


## Limitations

* Very early in development - may malfunction, or outright fail to build
* Supports only the P2

