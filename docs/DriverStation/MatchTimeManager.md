# Match Time Manager
![Static Badge](https://img.shields.io/badge/Minimum_Version-v2026.1.10-brightgreen)

```java
import com.btwrobotics.WhatTime.frc.DriverStation.MatchTimeManager;
```

---

## Methods
- `scheduleEventAtTime(timeRemaining, eventCommand, triggerName)`
    - `timeRemaining`: the time remaining in the match in seconds
    - `eventCommand`: a WPILib Command that will run at the time of the event
    - `triggerName`: an optional description of the trigger for reference in a List

---

## Variables
- `pendingTriggerDescriptions`: A `List<String>` of all events that have not been run.
- `completedTriggerDescriptions`: A `List<String>` of all events that have been run.
