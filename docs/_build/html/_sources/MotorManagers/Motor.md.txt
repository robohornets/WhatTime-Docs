# Motor
![Static Badge](https://img.shields.io/badge/Minimum_Version-v2026.2.1-brightgreen)

A wrapper for TalonFX motors to add better motor management and position handling.

```java
import com.btwrobotics.WhatTime.frc.MotorManagers.Motor;
```

## Constructor
```java
public Motor(
    TalonFX motor, 
    String canbus,
    boolean inverted
)
```
or
```java
public Motor(
    int deviceId, 
    String canbus, 
    boolean inverted
)
```

## Methods
`of(TalonFX motor, boolean inverted)` - Creates a Motor object from an existing TalonFX object.

`setInverted(boolean inverted)` - Sets the inversion status for the Motor object

```{note}
Position management allows controlling the position of the motor based on an internal or external encoder value. The motor will move to the position and hold in the correct spot.
```

`setFree(boolean free)` - Sets the free behaviour of the motor. If false, the motor will use position management with defined values. If true, the motor will spin freely (for applications like flywheels).

`setMinValue(double minValue)` - Sets the minimum limit for position management.

`setMaxValue(double maxValue)` - Sets the maximum limit for position management.

`setRange(double minValue, double maxValue)` - Sets the minimum and maximum limits for position management.

`setMinSpeed(double minSpeed)` - Sets the minimum speed of the motor. A value from -1.0 to 1.0.

`setMotorSpeed(double motorSpeed)` - Sets the speed of the motor. A value from -1.0 to 1.0.

`setHoldSpeed(double holdSpeed)` - Sets the hold speed of the motor for position management. The minimum speed before the mechanism starts to slip.

`setThreshold(double threshold)` - The threshold where the motor will stop running for position management.

`setPositionSupplier(DoubleSupplier positionSupplier)` - Sets a supplier from the encoder to tell the current position of the motor for position management.

`toggleEnabled()` - Toggles whether running the motor is enabled.

`toggleEnabled(Boolean enabled)` - Sets the motor's enabled state.

`drive(boolean reverse)` - Runs the motor in free mode with speed of `setMotorSpeed()`.

`drive(double speed)` - 

`goTo(double target)` - 

`setTarget(double target)` -

`setNeutralMode(NeutralModeValue neutralModeValue)` - 

`brakelessReset(double durationSeconds)` - 


