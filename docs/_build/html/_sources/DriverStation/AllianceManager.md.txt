# Alliance Manager
![Static Badge](https://img.shields.io/badge/Minimum_Version-v2026.1.10-brightgreen)

```java
import com.btwrobotics.WhatTime.frc.DriverStation.AllianceManager;
```

---

## Methods
- `getCurrentAlliance()`
    - Gets the current alliance for the robot from DriverStation.
    - Returns the current alliance as `Optional<Alliance>`
- `getOpposingAlliance()`
    - Gets the opposing alliance for the robot from DriverStation.
    - Returns the opposing alliance as `Optional<Alliance>`
- `toggleAlliance(alliance)`
    - Takes in an `Alliance` or `Optional<Alliance>` object
    - Returns the opposite alliance of the input as an `Alliance` or `Opptional<Alliance>` respectively

