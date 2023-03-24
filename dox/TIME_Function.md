---
title: "%TIME Function"

Id: TIME_Function
TocParent: Functions_overview
TocOrder: 45


---

**%TIME** [built-in function](Functions_overview.html) converts the value of an expression from character, numeric, or timestamp data to type time. If no expression is specified, the current system time is returned. 
<pre class="prettyprint">
 **%TIME**  ((Expression {, <u>*ISO</u> | *HMS | *USA | *EUR | *JIS}))<br /></pre>

### Parts

**Expression** 

Optional. *Expression* can be character, numeric, or timestamp data to be converted to type time.


***ISO, *HMS, *USA, *EUR, *JIS** 

Optional. This is the [time format](Time_Formats.html) of character and numeric input. If *Expression* is a timestamp, do not specify this parameter as the system knows the format of the input. The default for character and numeric input is *ISO format.


### Remarks
The converted value remains unchanged but is returned as a time. If no *Expression* is specified, the current system time is returned. Regardless of the input format, the resulting value is *ISO time format. 

### See Also
[Built-in Function Overview](Functions_overview.html)
[Time Formats](Time_Formats.html)
[%TIMESTAMP](TIMESTAMP_Function.html)
[%DATE](DATE_Function.html) 
