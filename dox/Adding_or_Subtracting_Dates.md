---
title: Adding or Subtracting Dates

Id: Adding_or_Subtracting_Dates
TocParent: aerLrfDateandTimeMain
TocOrder: 0


---

When adding (or subtracting) a duration in months to (or from) a date, the general rule is that the month portion is increased (or decreased) by the number of months in the duration, and the day portion is unchanged. The exception to this is when the resulting day portion would exceed the actual number of days in the resulting month. In this case, the resulting day portion is adjusted to the actual month end date. 

**For Example:** 

- Adding one month to "97/08/30" (*YMD format) results in "97/09/30", as expected. The resulting month portion has been increased by 1; the day portion is unchanged. On the other hand, adding one month to "97/08/31" results in "97/09/30". The resulting month portion has been increased by 1 and the resulting day portion has been adjusted because September only has 30 days.
- Subtracting one month from "95/03/30" yields "95/02/28". In this case, the resulting month portion is decreased by 1 and the resulting day portion adjusted because February has only 28 days (in non-leap years).
- Adding one year to "92/02/29" results in "93/02/28", an adjusted value since the resulting year is not a leap year.

### See Also
[Date and Time](aerLrfDateandTimeMain.html)
[ADDDUR](ADDHANDLER.html)
[Calculating Durations between Dates](Calculating_Durations_between_Dates.html)
[SUBDUR](SUBDUR.html) 
