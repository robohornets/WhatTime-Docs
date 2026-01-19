# Motor Wrapper
![Static Badge](https://img.shields.io/badge/Minimum_Version-v0.1.1-brightgreen)

```java
import com.btwrobotics.WhatTime.frc.MotorManagers.MotorWrapper;
```
The MotorWrapper class wraps a TalonFX motor object and allows direction inversion logic to be built-in to simplify use across other classes.

## Constructor
Creates a new MotorWrapper with the specified motor and inversion setting:
- motor: The TalonFX motor instance.
- inverted: Whether the motor's direction should be inverted by default.

```java
public MotorWrapper(TalonFX motor, boolean inverted)
```

## Static Helper Method
Convenience method for creating a MotorWrapper using a static syntax:
```java
public static MotorWrapper of(TalonFX motor, boolean inverted)
```
## Methods
### Applies speed to the motor, respecting the inversion setting:
```java
public void set(double speed)
```

### Return the underlying TalonFX motor object:
```java
public TalonFX getMotor()
```

### Returns whether this wrapper inverts the motor direction:
```java
public boolean isInverted()
```

## Example Usage
```java
TalonFX myMotor = new TalonFX(5);
MotorWrapper wrapper = new MotorWrapper(myMotor, true);

// Or using the static constructor
MotorWrapper wrapper2 = MotorWrapper.of(new TalonFX(6), false);

wrapper.set(0.5); // Sets the motor to -0.5 due to inversion
boolean inverted = wrapper.isInverted(); // true
```