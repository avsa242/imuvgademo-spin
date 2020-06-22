# imu-demo-vga
--------------

This is a P2X8C4M64P/Propeller 2 demo application that displays live data from an IMU in a graphical representation (e.g., orientation, movement rate, etc)

**IMPORTANT**: This software is meant to be used with the ~~[spin-standard-library](https://github.com/avsa242/spin-standard-library) (P8X32A) or~~ [p2-spin-standard-library](https://github.com/avsa242/p2-spin-standard-library) (P2X8C4M64P). Please install the applicable library first before attempting to use this code, otherwise you will be missing several files required to build the project.

## Videos

* [LSM9DS1 Gyro](https://youtu.be/nFppKTgk1ds)
* [MPU9250 Gyro](https://youtu.be/OZ-gQdGFW-k)
* [MPU9250 Accel](https://youtu.be/X_TVRA0FTkQ)

## Salient Features

* ``AccelRay()``: Displays 3DoF accelerometer data as rays radiating from the screen center outwards in proportion with acceleration experienced by each axis (currently static orientation)
* ``GyroRay()``: Display 3DoF gyroscope data as above, but in a pseudo-3D fashion. Trig is used to locate the endpoints of the lines following an elliptical path around the center of the screen, with a circle also attached to the endpoint. The circle radius changes with movement to give a slight sense of depth.

## Requirements

P2/SPIN2:
* p2-spin-standard-library
* P2EVAL board and Parallax A/V accessory board #64006-ES or equivalent

Supported IMUs:
* MPU9250 (I2C)
* LSM9DS1 (3w SPI)

## Compiler Compatibility

* ~~P1/SPIN1: OpenSpin (tested with 1.00.81)~~ _(not yet implemented)_
* P2/SPIN2: FastSpin (tested with 4.1.10-beta)
* ~~BST~~ (incompatible - no preprocessor)
* ~~Propeller Tool~~ (incompatible - no preprocessor)
* ~~PNut~~ (incompatible - no preprocessor)

## Limitations

* Very early in development - may malfunction, or outright fail to build
* Supports only the P2
* Plots only using raw data

## TODO

- [ ] Improve output of existing plotting routines
- [ ] Add routines for plotting magnetometer data
- [ ] Add ability to change settings at runtime
- [ ] Add ability to calibrate IMU
- [x] Add screenshots and example video footage
- [ ] Port to P1/SPIN1
- [ ] Add support for logging of data to flash/SD

Add support for other IMUs and motion sensors:
- [x] LSM9DS1
- [ ] LIS3DH
- [ ] ADXL345
- [ ] L3G4200D
- [ ] MMA7455
