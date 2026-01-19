# About MotorManagers
In WhatTime, MotorManagers are a set of classes that allow for simplified control of motors. Currently, only TalonFX motors are supported, but support for more types is planned.

---

## Classes
- `MotorWrapper`: Wraps a TalonFX object and allows simplified inversion of the motor's direction.
- `PositionManager`: Takes in parameters and creates commands to move motors to certain positions based on sensor input.
- `BrakelessReset`: Disables brakes, allows mechanism to fall to a neutral position, resets the motor position, and then re-enables brakes.