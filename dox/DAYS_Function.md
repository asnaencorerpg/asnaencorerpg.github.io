---
title: "%DAYS Function"

Id: DAYS_Function
TocParent: Functions_overview
TocOrder: 6


---

**%DAYS** [built-in function](Functions_overview.html) converts a number into a duration that can be added to a date or timestamp value. 

```

 **%DAYS (Number)** 
        
```

### Parts

**Number** 

Required. The number to be converted to duration and added to or subtracted from a date or timestamp value.


### Remarks
**%DAYS** can only be the right-hand value in an addition or subtraction operation. The left-hand value must be a date or timestamp. The result is a date or timestamp value with the appropriate number of days added or subtracted. For a date, the resulting value is *ISO format. 

### See Also
[Built-in Function Overview](Functions_overview.html)

[Adding or Subtracting Dates](Adding_or_Subtracting_Dates.html)

[%DIFF](DIFF_Function.html)

[%HOURS](HOURS_Function.html)

[%MINUTES](MINUTES_Function.html)

[%MONTHS](MONTHS_Function.html)

[%MSECONDS](MSECONDS_Function.html)

[%SECONDS](SECONDS_Function.html)

[%YEARS](YEARS_Function.html) 
