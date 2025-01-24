---
title: "%TLOOKUP Function"

Id: TLOOKUP_Function
TocParent: Functions_overview
TocOrder: 47


---

<span style="FONT-WEIGHT: bold">%TLOOKUP</span> [built-in function](Functions_overview.html) sets the current table element to the element that satisfies the condition and returns the value ***ON** , otherwise, ***OFF** is returned if no match is found. 

```
%TLOOKUP (Argument, Search_Table  {, Alternate_Table} ) 
 %TLOOKUPLT (Argument, Search_Table  {, Alternate_Table} ) 
 %TLOOKUPGE (Argument, Search_Table  {, Alternate_Table} ) 
 %TLOOKUPGT (Argument, Search_Table  {, Alternate_Table} ) 
 %TLOOKUPLE (Argument, Search_Table  {, Alternate_Table} ) 
```

### Parameters

**Argument, Search_Table** 

Required. Contains the search argument and the name of the table to be searched. Both must be the same type but do not need to be the same length.


**Alternate_Table** 

Optional. Contains an alternate table name.


### Remarks
This function sets the current table element to the element that satisfies the condition, sets the current table element for the ***Alternate-Table*** to the same element, and returns the value ***ON** as follows: 

- %TLOOKUP - for an exact match.
- %TLOOKUPLT - for the value that is closest to,  but less than ***Argument*** 
                in value.
- %TLOOKUPLE - for an exact match, or the value that is closest to, but
                is less than ***Argument*** 	in value.
- %TLOOKUPGT - for the value that is closest to, but greater than ***Argument*** 
                in value.
- %TLOOKUPGE - for an exact match, or the value that is closest to, but
                greater than ***Argument***  in value.

If no match is found, ***OFF** is returned.

Unlike the [LOOKUP](LOOKUP.html) op code, **%TLOOKUP** only applies to tables. To look up a value in an array, use the [%LOOKUP](LOOKUP_Function.html) function. 

Note [%FOUND](FOUND_Function.html) and [%EQUAL](EQUAL_Function.html) are **NOT** set following a **%TLOOKUP** operation. 

### See Also
[Built-in Function Overview](Functions_overview.html)

[LOOKUP](LOOKUP.html)

[%EQUAL](EQUAL_Function.html)

[%FOUND](FOUND_Function.html)

[%LOOKUP](LOOKUP_Function.html) 
