# NetworkTablesUtil
![Static Badge](https://img.shields.io/badge/Minimum_Version-v2026.1.7-brightgreen)

```java
import com.btwrobotics.WhatTime.frc.DashboardManagers.NetworkTablesUtil;
```
The NetworkTablesUtil class provides an easy way to display data on NetworkTables. It supports multiple data types with overloaded put() methods.

---

## Methods
### Put a number to NetworkTables using a key:
```java
public static void put(String key, double value)
```
or to specify a custom table:
```java
public static void put(String table, String key, double value)
```

### Put a string to the NetworkTables using a key:
```java
public static void put(String key, String value)
```
or to specify a custom table:
```java
public static void put(String table, String key, String value)
```

### Put a boolean to the NetworkTables using a key:
```java
public static void put(String key, boolean value)
```
or to specify a custom table:
```java
public static void put(String table, String key, boolean value)
```

### Puts a generic object to the NetworkTables with type detection and formatting:
```java
public static void put(String key, Object value)
```
or to specify a custom table:
```java
public static void put(String table, String key, Object value)
```

---

## Example Usage
```java
NetworkTablesUtil.put("Arm Angle", 37.5);
NetworkTablesUtil.put("Status", "Retracted");
NetworkTablesUtil.put("Intake Active", true);

Object customValue = 42;
NetworkTablesUtil.put("Custom Number", customValue);

NetworkTablesUtil.put("Custom Table Name", "Custom Number", customValue);
```