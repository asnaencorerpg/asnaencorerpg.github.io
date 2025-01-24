---
title: "%FOUND Function"

Id: FOUND_Function
TocParent: Functions_overview
TocOrder: 21


---

**%FOUND** [built-in function](Functions_overview.html) returns **True** if the most recent relevant file operation found a record, a string operation found a match, or a search operation found an element. Otherwise, this function returns False. 

```
%FOUND {(File_name)}
```

### Parameters

**File_name** 

Optional. The name of the file.


- If the **file** _ **name** parameter is not specified, then it returns the value set for the most recent relevant operation.
- If the **file** _ **name** parameter is specified, then it applies to the most recent relevant operation on that file.


### Remarks
For **file** operations, % **FOUND** is opposite in function to the "no record found NR" indicator, or the NotFnd parameter. 

For **string** operations, % **FOUND** is the same in function as the "found FD" indicator, or the Fnd parameter. 

For the **LOOKUP** operation, % **FOUND** returns True if the operation found an element satisfying the search conditions. 

The operations that set **%FOUND** are:<br /> **File operations:** 

- [CHAIN](CHAIN.html) (Random Retrieval from a File)
- [DELETE](DELETE.html) (Delete Record)
- [SETGT](SETGT.html) (Set Greater Than)
- [SETLL](SETLL.html) (Set Lower Limit)

**String operations:** 

- [CHECK](CHECK.html) (Check Characters)
- [CHECKR](CHECKR.html) (Check Reverse)
- [SCAN](SCAN.html) (Scan String)

Built-in function [%SCAN](SCAN_Function.html) does not change the value of **%FOUND** . 

**Search operations:** 

- [LOOKUP](LOOKUP.html) (Look Up a Table or Array Element)

### See Also
[Built-in Function Overview](Functions_overview.html)

[%SCAN Function](SCAN_Function.html)

[CHAIN](CHAIN.html)

[CHECK](CHECK.html)

[CHECKR](CHECKR.html)

[DELETE](DELETE.html)

[LOOKUP](LOOKUP.html)

[SCAN](SCAN.html)

[SETGT](SETGT.html)

[SETLL](SETLL.html)

[IsFound Property](IsFoundPropertyDbFileClass.html) 
