---
title: "%TIMESTAMP Function"

Id: TIMESTAMP_Function
TocParent: Functions_overview
TocOrder: 46


---

**%TIMESTAMP** [built-in function](Functions_overview.html) converts the value of an expression from character, numeric, or date data to type timestamp. If no expression is specified, the current system timestamp is returned. 
<pre class="prettyprint">
 **%TIMESTAMP**  ((Expression {, <u>*ISO</u> | *ISO0}))<br /></pre>

### Parts

**Expression** 

Optional. *Expression* can be character, numeric, or date data to be converted to type timestamp.


***ISO, *ISO0** 

Optional. This is the timestamp format. 

- For character expressions, *ISO or *ISO0 is valid.
- For numeric expressions, you need not specify the timestamp format as only *ISO
                        (the default) is valid.
- For date expressions, do not specify the timestamp format. The date is
                        converted from it's current format to *ISO.


### Remarks
If no *Expression* is specified, the current system timestamp is returned. Regardless of the input format, the resulting value is *ISO format. 

### See Also
[Built-in Function Overview](Functions_overview.html)

[Timestamp Data Types](Timestamp_Data_Type.html)

[%TIME](TIME_Function.html)

[%DATE](DATE_Function.html) 
