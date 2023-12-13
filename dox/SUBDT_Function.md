---
title: "%SUBDT Function"

Id: SUBDT_Function
TocParent: Functions_overview
TocOrder: 43


---

<span style="FONT-WEIGHT: bold">%SUBDT</span> [built-in function](Functions_overview.html) extracts a portion of a date, time, or timestamp and returns an unsigned numeric value. 

```
%SUBDT (Value, {*MSECONDS | *SECONDS | *MINUTES | *HOURS | *DAYS | *MONTHS | *YEARS}) 
        
```

### Parts

**Value** 

Required. A date, time, or timestamp type value.


***MSECONDS, *SECONDS, *MINUTES, *HOURS, *DAYS, *MONTHS, *YEARS** 

Indicates the portion of *value* you want to extract. The following table indicates the valid values for the *value* type: 

- For Date, you can specify *DAYS, *MONTHS, or *YEARS.
- For Time, you can specify *SECONDS, *MINUTES, or *HOURS.
- For Timestamp, you can specify *MSECONDS, *SECONDS, *MINUTES, *HOURS, *DAYS, *MONTHS, or *YEARS.


### Remarks
This function returns an unsigned numeric value and will always return a 4 digit year. 

### See Also
[Built-in Function Overview](Functions_overview.html)

[%DIFF](DIFF_Function.html) 
