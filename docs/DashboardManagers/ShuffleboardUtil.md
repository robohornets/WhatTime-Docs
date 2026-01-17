# ShuffleboardUtil
![Static Badge](https://img.shields.io/badge/Minimum_Version-v0.1.1-brightgreen)

```{note}
[Shuffleboard](https://docs.wpilib.org/en/stable/docs/software/dashboards/shuffleboard/index.html) and [SmartDashboard](https://docs.wpilib.org/en/stable/docs/software/dashboards/smartdashboard/index.html#smartdashboard) have already been deprecated. They will be removed for the 2027 season. As a result, this part of the library will only be available through 2026. We recommend switching to NetworkTablesUtil for future support.
```

```java
import com.btwrobotics.WhatTime.frc.DashboardManagers.ShuffleboardUtil;
```
The ShuffleboardUtil class provides an easy way to display data on the Shuffleboard using the WPILib SmartDashboard system. It supports multiple data types with overloaded put() methods.

## Methods
### Put a number to Shuffleboard using a key:
```java
public static void put(String key, double value)
```
or to specify a custom table:
```java
public static void put(String table, String key, double value)
```

### Put a string to Shuffleboard using a key:
```java
public static void put(String key, String value)
```
or to specify a custom table:
```java
public static void put(String table, String key, String value)
```

### Put a boolean to Shuffleboard using a key:
```java
public static void put(String key, boolean value)
```
or to specify a custom table:
```java
public static void put(String table, String key, boolean value)
```

### Puts a generic object to Shuffleboard with type detection and formatting:
```java
public static void put(String key, Object value)
```
or to specify a custom table:
```java
public static void put(String table, String key, Object value)
```

## Example Usage
```java
ShuffleboardUtil.put("Arm Angle", 37.5);
ShuffleboardUtil.put("Status", "Retracted");
ShuffleboardUtil.put("Intake Active", true);

Object customValue = 42;
ShuffleboardUtil.put("Custom Number", customValue);
```