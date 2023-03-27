---
title: Calculating Durations between Dates

Id: Calculating_Durations_between_Dates
TocParent: aerLrfDateandTimeMain
TocOrder: 1


---

Use [SUBDUR](SUBDUR.html) to calculate a duration by subtracting two dates, times, or timestamps. The result of the calculation is in whole units, and any rounding is done downwards. The calculation of durations includes microseconds. 

### Example
A duration of 59 minutes requested in hours will result in 0 hours. 

A duration is 374 days requested in years yields 1 complete year because there are 1.02 years in 374 days. 

If adjustment takes place on a date-time [addition or subtraction](Adding_or_Subtracting_Dates.html), then a subsequent calculation will most likely result in a different duration than the one original one added or subtracted. This is because the subsequent duration will no longer contain a complete unit, and rounding down will yield one unit less than expected. 

### See Also
[Date and Time](ecrLrfDateandTimeMain.html)

[ADDDUR](ADDHANDLER.html)

[Adding or Subtracting Dates](Adding_or_Subtracting_Dates.html)

[SUBDUR](SUBDUR.html) 
