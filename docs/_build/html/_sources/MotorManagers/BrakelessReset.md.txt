# Brakeless Reset
![Static Badge](https://img.shields.io/badge/Minimum_Version-v0.1.1-brightgreen)

```{note}
This implementation will soon be replaced by a class more similar to PositionManager
```

```java
import com.btwrobotics.WhatTime.frc.MotorManagers.BrakelessReset;
```
BrakelessReset is a WPILib Command that temporarily disables brake mode on a list of motors, allowing them to coast to a natural resting position. This is useful for recalibrating or zeroing encoders after the motors have moved freely.

## Constructor
```java
public BrakelessReset(double duration, List<BrakelessReset.MotorResetPair> pairs)
```
- **duration**: How long (in seconds) to wait before running the reset actions.
- **pairs**: A list of motor/action pairs that define which motors to set to coast and what reset action to run.

## MotorResetPair
```java
public static class MotorResetPair {
    public final MotorWrapper motor;
    public final Runnable resetAction;
}
```
Each motor is bundled with a Runnable that executes when the duration ends. This allows encoder zeroing or any custom logic.

## Lifecycle Methods
```initialize()```: Sets all motors to Coast mode and starts a timer.

```isFinished()```: Returns true once the specified duration has elapsed.

```end()```: Runs each resetAction when the command finishes or is interrupted.

Example Usage
```java
MotorWrapper armMotor = new MotorWrapper(new TalonFX(3), false);
Runnable zeroEncoder = () -> armMotor.getMotor().setPosition(0);

BrakelessReset.MotorResetPair pair = new BrakelessReset.MotorResetPair(armMotor, zeroEncoder);
BrakelessReset resetCommand = new BrakelessReset(1.5, List.of(pair));
```
This command disables braking on armMotor for 1.5 seconds, allowing the arm to drop to its lowest point, and then zeroes the encoder.