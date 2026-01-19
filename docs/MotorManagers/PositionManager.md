# Position Manager
![Static Badge](https://img.shields.io/badge/Minimum_Version-v0.1.1-brightgreen)

```java
import com.btwrobotics.WhatTime.frc.MotorManagers.PositionManager;
```
PositionManager takes in an array of MotorWrapper objects. It will then automatically move the motors to the specified position. All motors will be moved to the same position, so it is important to use the ```inverted``` parameter if necessary.

This class does not work well if the sensor only ranges from 0 to 1 and resets. If that is the case, you will either need to limit it to a minimum and maximum within the same rotation or create a method to count the number of rotations.

---

## Constructor
```java
public PositionManager(
    double minValue,
    double maxValue,
    List<MotorWrapper> motors,
    double motorSpeed,
    double holdSpeed,
    double threshold,
    Supplier<Double> currentAngleSupplier
)
```

- `minValue`
    - The lowest allowed value for the motors. This should be found manually before running by starting the motor at zero, moving it to the desired position, and viewing the value in ShuffleBoard.
- `maxValue`
    - The highest allowed value for the motors. This should be found manually before running by starting the motor at zero, moving it to the desired position, and viewing the value in ShuffleBoard.
- `motors`
    - A list of MotorWrapper objects. All these motors will be moved to the desired position.
- `motorSpeed`
    - A double value that will be set for the speed of the motors. Individual motor direction is automatically managed based on the `inverted` parameter of the MotorWrapper. Positive is the forwards direction. Negative is backwards. These still respect the `inverted` parameter though. That means an inverted motor set to a negative speed turns the same way as a non-inverted motor set to a positive speed.
- `holdSpeed`
    - If the brakes are not enough to hold up the part, you can set a hold speed. You should find this by starting small and testing higher values until it no longer falls. It will set the motors to this speed whenever they are not running another command.
- `threshold`
    - The range the method will deem "acceptable" before ending. A smaller value will result in better precision, but is also more likely to over or undershoot requiring more time and a lower motor speed. It is very important to get this value correct for everything to work well.
- `currentAngleSupplier`
    - Gets an updating angle value from a sensor.

---

## Methods
`move()`: Moves to a specified position

`getTarget()`: Returns the PositionManager target as a double

`stop()`: Sets all motors to the specified hold speed

---

## Example Usage
```java
PositionManager positionManager = new PositionManager(
    0.0,
    50.0,
    List.of(
        new MotorWrapper(leftMotor, true),
        new  MotorWrapper(rightMotor, false)
    ),
    0.5,
    0.05,
    2.0,
    () -> subsystem.getDoubleForSupplier()
)
```

```java
positionManager.move(targetPosition)
```
This will create two new MotorWrapper objects and set the rest of the parameters to run the position manager. 

**Note: Generally, MotorWrappers should not be created inside the List. This is only for demonstration purposes. Instead, they should be defined once and referenced throughout the code.**


To create a supplier, we can use a lambda as seen in the last line. This automatically converts the method—which returns a double—into Supplier\<Double\>.