# 2026 - RebuiltHubManager
![Static Badge](https://img.shields.io/badge/Minimum_Version-v2026.1.10-brightgreen)

```java
import com.btwrobotics.WhatTime.frc.YearlyMethods.Rebuilt.RebuiltHubManager;
```
RebuiltHubManager is a class that simplifies management of hub related features for the 2026 game. It is able to track which alliance has an inactive hub first as well as automatically switching the active hub as it changes throughout the match.

---

## Constructor
```java
public RebuiltHubManager(MatchTimeManager matchTimeManager) {
    this.matchTimeManager = matchTimeManager;
}
```
```java
RebuiltHubManager rebuiltHubManager = new RebuiltHubManager(matchTimeManager);
```

- `matchTimeManager`: A class from WhatTime that keeps track of time in the current match.

---

## Methods & Usage

For this class to work, you must call the methods `updateInitialInactiveAlliance()` and `scheduleAllInactiveHubChanges()` in your robot code.

### Updates which alliance is inactive first based on the results from autonomous:
```java
public void updateInitialInactiveAlliance()
```

**Example Usage in RobotContainer.java:**
```java
@Override
public void teleopInit() {
    rebuiltHubManager.updateInitialInactiveAlliance();
}
```

---

### Returns the alliance that is inactive first:
```java
public Optional<Alliance> getInactiveFirstAlliance()
```

```{note}
Requires v2026.1.15 or later
```

---

### Returns true if the current team's hub is active:
```java
public boolean hubIsActive()
```

---

### Add triggers at times to change the hub status:
This should be called only once.

```java
public void scheduleAllInactiveHubChanges()
```

**Example Usage in RobotContainer.java:**
```java
@Override
public void robotInit() {
    rebuiltHubManager.scheduleAllInactiveHubChanges();
}
```

---

### Put a list of all past and upcoming events to NetworkTables:
```java
putPhasesToNetworkTables()
```

**Example Usage in RobotContainer.java:**
```java
@Override
public void robotPeriodic() {
    rebuiltHubManager.putPhasesToNetworkTables();
}
```