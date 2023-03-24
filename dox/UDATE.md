---
title: UDATE

Id: UDATE
TocParent: aerLrfOpCodesMain
TocOrder: 1580


---

**UDATE** is a special word that allows the programmer to supply the date at run-time. These special words give the date and time when the project was started. Use the [TIME](TIME.html) operation code to obtain the current time and date while the program is running. 

### Remarks
These special words are provided in Year/Month/Day date format. 

**UDATE** gives a 6-character numeric date field. 

**UDATE** can be edited by using the **Y edit code** . 

User date fields are not **date** data type fields, but are numeric fields. 

### Example
IOFIELD1 = UDATE 

### See Also
[UDAY](UDAY.html)
[UMONTH](UMONTH.html)
[UYEAR](UYEAR.html)
[TIME](TIME.html) 
