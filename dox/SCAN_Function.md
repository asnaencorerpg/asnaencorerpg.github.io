---
title: "%SCAN Function"

Id: SCAN_Function
TocParent: Functions_overview
TocOrder: 38


---

**%SCAN** [built-in function](Functions_overview.html) returns the first position of the search argument in the source string, or 0 if it was not found. If the start position is specified, the search begins at the starting position. The result is always the position in the source string even if the starting position is specified. The starting position defaults to 1. 

```

 ** *<pos>*  = %SCAN (SearchArgument, SourceString,**  {Start})
```

### Parts

**SearchArgument** 

Required. Must be of type character.


**SourceString** 

Required. Must be the same type as the first parameter.


**Start** 

Optional. Must be numeric with zero decimal positions.


### Returns
***<pos>***  is an unsigned integer value
        containing the first position of the **SearchArgument**  in **SourceString** .  If the **SearchArgument**  is not
        found, 0 will be returned.

### Remarks
When any parameter is variable in length, the values of the other parameters are checked against the current length, not the maximum length. 

This built-in function can be used anywhere that an unsigned integer expression is valid. 

Unlike the [SCAN](SCAN.html) operation code, % **SCAN** cannot return an array containing all occurrences of the search string and its results cannot be tested using the [%FOUND](FOUND_Function.html) built-in function. 

### Example

```
BEGSR Scan_Ex
 DclConst Name(Source) Value("This is a test.")
 DclFld Name(Pos) Type(*ZONED) Len(5,0)
 Pos = %Scan ("est", Source, 5)
 Msgbox Pos 
ENDSR
```

### See Also
[Built-in Function Overview](Functions_overview.html)
[%FOUND Function](FOUND_Function.html)
[SCAN](SCAN.html) 
