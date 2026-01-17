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

`matchTimeManager`: A class from WhatTime that keeps track of time in the current match.

---

## Methods & Usage
`updateInitialInactiveAlliance()`: Updates which alliance is inactive first based on the results from autonomous.

```java
@Override
public void teleopInit() {
    rebuiltHubManager.updateInitialInactiveAlliance();
}
```

---

`scheduleAllInactiveHubChanges()`: Adds triggers at times to change the hub status. Should be called only once.

```java
@Override
public void robotInit() {
    rebuiltHubManager.scheduleAllInactiveHubChanges();
}
```

---

`hubIsActive()`: Returns true if the hub is active for the current alliance.

```java
rebuiltHubManager.hubIsActive();
```

---

`putPhasesToNetworkTables()`: Puts a list of all past and upcoming events to NetworkTables.
```java
@Override
public void robotPeriodic() {
    rebuiltHubManager.putPhasesToNetworkTables();
}
```