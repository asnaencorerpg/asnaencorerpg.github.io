---
title: "%DATE Function"

Id: DATE_Function
TocParent: Functions_overview
TocOrder: 5


---

**%DATE** [built-in function](Functions_overview.html) converts the value of the expression from character, numeric, or timestamp data to type date. If no expression is specified, the current system date is returned. 

```

 **%DATE**  ((Expression {, <u>*ISO</u> | *JUL | *USA | *EUR | *JIS | *MDY | *DMY | *YMD }))
```

### Parts

**Expression** 

Optional. *Expression* can be character, numeric, or timestamp data to be converted to type date. 

The second parameter is the [date format](Date_Formats.html) of character and numeric input. If ***Expression*** is a timestamp, [*DATE](StarDate.html), or [UDATE](UDATE.html), do not specify this parameter as the system knows the format of the input. Regardless of the input date format, the returned date is *ISO format.


### Remarks
If no parameters are present, this function returns the current system date in *ISO format. 

### See Also
[Built-in Function Overview](Functions_overview.html)
[Date Formats](Date_Formats.html)
[Default Values Date_Formats](Default_Values_for_all_Date_Formats.html)
[*DATE](StarDate.html)
[UDATE](UDATE.html)
[%TIME](TIME_Function.html)
[%TIMESTAMP](TIMESTAMP_Function.html) 
