---
title: Rules for User Date

Id: Rules_for_User_Date
TocParent: aerLrfVariablesMain
TocOrder: 16


---

Use the following rules when using user date special words: 

- User date fields are numeric fields, not [Date Data Type](Date_Data_Type.html) fields.
- For an interactive job or batch program, the user date special words are set to the value of the job date when the program starts running in the system. The value of the user date special words are not updated during program processing, even if the program runs past midnight or if the job date is changed. Use the [TIME](TIME.html) operation code to obtain the time and date while the program is running.

The user date fields cannot be modified. This means they cannot be used:

- As input fields
- In the result field of calculations
- As F1 of [DCLPARM](DCLPARM.html) operations
- As Index of [LOOKUP](LOOKUP.html) operations

### See Also
[Variables](aerLrfVariablesMain.html)

[Date Data Type](Date_Data_Type.html)

[*Date](StarDate.html)

[*Day](StarDay.html)

[DCLPARM](DCLPARM.html)

[Figurative Constants Rules](Fig_Constants_Rules.html)

[LOOKUP](LOOKUP.html)

[*Month](StarMonth.html)

[TIME](TIME.html) 
