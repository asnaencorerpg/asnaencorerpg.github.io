---
title: "%EQUAL Function"

Id: EQUAL_Function
TocParent: Functions_overview
TocOrder: 19


---

<span style="FONT-WEIGHT: bold">%EQUAL</span> [built-in function](Functions_overview.html) returns **True** if the most recent relevant operation found an exact match; otherwise, it returns False. 

```
% **EQUAL**  {(File_name)}
```

### Parts

**File_name** 

Optional. The name of the file.


### Remarks
The operations that set **%EQUAL** are: 

- [SETLL](SETLL.html) (Set Lower Limit)
- [LOOKUP](LOOKUP.html) (Look Up a Table or Array Element)

If % **EQUAL** is used without the optional **File_name** parameter, then it returns the value set for the most recent relevant operation. 

For the **SETLL** operation, this function returns True if a record is present whose key or relative record number is equal to the search argument. 

For the **LOOKUP** operation with the EQ indicator specified, this function returns True if an element is found that exactly matches the search argument. 

If a file name is specified, this function applies to the most recent **SETLL** operation for the specified file. This function is allowed only for files that allow the **SETLL** operation code. 

### See Also
[Built-in Function Overview](Functions_overview.html)
[LOOKUP](LOOKUP.html)
[SETLL](SETLL.html)
[IsEqual Property](IsEqualPropertyDbFileClass.html) 
