---
title: "%CHECKR Function"

Id: CHECKR_Function
TocParent: Functions_overview
TocOrder: 4


---

**%CHECKR** [built-in function](Functions_overview.html) returns the last position of the string ***Base*** that contains a character that does NOT appear in string ***Comparator*** . If all of the characters in ***Base*** are also in ***Comparator*** , this function returns 0. 

```
%CHECKR 
 (Comparator, Base , {Start})   
```

### Parameters

**Comparator** 

Required. Can be a field name, array element, named constant, data structure name, data structure subfield name, literal, or table name; to compare against ** *Base* ** .


**Base** 

Required. Can be any valid numeric or character expression to compare with ** *Comparator* ** , and must be of the same type as ***Comparator*** .


**Start** 

Optional. Contains the position, relative to the leftmost position in ***Base*** , in which to start. If specified, ***Start*** must be a non-float numeric with zero decimal positions. If not specified, the starting position defaults to the length of the string.


### Remarks
Checking begins at the ***Start*** or rightmost position of ** *Base* ** and continues character by character right to left. Each character of ** *Base* ** is compared with the ***Comparator*** characters and if a match exists, the next ***Base*** character is checked. If no match is found, the function returns the position within ***Base*** of the non-matched character. If all of the characters in ***Base*** are also in ***Comparator*** , this function returns 0. Note the return value is relative to the left although checking is done from the right. 

The **%CHECKR** command **cannot** accept *BOOLEAN and *IND data types. 

### See Also
[Built-in Function Overview](Functions_overview.html)

[CHECK](CHECK.html)

[CHECKR](CHECKR.html)

[%CHECK](CHECK_Function.html) 
