---
title: "*Date"

Id: StarDate
TocParent: aerLrfFigConstantsMain
TocOrder: 4


---

* **Date** is a special word that allows the programmer to supply the date at run-time. These special words give the date and time when the project was started. Use the [TIME](TIME.html) operation code to obtain the current time and date while the program is running. 

### Remarks
The user dates can be written at output time, and are written in the format specified by the control specification. 

These special words can be used in three different date formats: 

- Month/day/year
- Year/month/day
- Day/month/year

* **Date** gives an 8-character (4-digit year) numeric date field. 

* **Date** can be edited by using the **Y edit code** . 

User date fields are not ***Date data type** fields, but are numeric fields. 

### Example
IOFIELD1 = *DATE 

### See Also
[Figurative Constants](aerLrfFigConstantsMain.html)

[*Day](StarDay.html)

[*Month](StarMonth.html)

[TIME](TIME.html)

[*Year](StarYear.html)

[Figurative Constants Rules](Fig_Constants_Rules.html) 
