---
title: LOOKUP

Id: LOOKUP
TocParent: aerLrfOpCodesMain
TocOrder: 1200


---

Searches for a particular element in an array or table.

```
LOOKUP
Source (Character Expression) Table  (table name | Array)
Result (Character Expression)
FndIndex (Numeric Variable)  
Hi (Indicator Variable)
Lo (Indicator Variable)
Eq (Indicator Variable)
```

### Parameters

**Source** 

Required. Contains the search argument or data for which you want to find a match in the single-dimension array or table named. If **Source** is a table name, the search argument used is the element of the table last selected in a **LOOKUP** operation. The array or table to be searched is specified in **Table** .


**Table** 

Required. Specifies the array or table to be searched. If the table has not been selected before, the first element in the table is used.


**Result** 

Optional. Must be a table name if **Table** contains a table name. Otherwise, the result should be left blank.


**FndIndex** 

Optional. Returns the index value of the element located. The value is relative to zero. The index is set equal to zero if the search is unsuccessful.


**Hi, Lo, Eq** 

Optional. At least one conditional indicator must be set or an error message will occur. In addition, the **Hi** and **Lo** indicators cannot be specified simultaneously. The compiler assumes a sorted sequenced array or table when a high or low indicator is specified for the LOOKUP operation. The **LOOKUP** operation searches for an entry that satisfies the low/equal or high/equal condition with equal given priority. 

**Hi -** Instructs the program to find the entry that is nearest to, yet higher in sequence than, the search argument. When a higher entry is found, the high indicator is set on. For example, if an ascending array contains the values A B C C C D E and the search argument is B, then the first C will satisfy the search. If a descending array contains E D C C C B A and the search argument is B, then the last C will satisfy the search. If an entry higher than the search argument is not found in the array or table, the search is unsuccessful. 

**Lo -** Instructs the program to find the entry that is nearest to, yet lower in sequence than, the search argument. When a lower entry is found, the low indicator is set on. For example, if an ascending array contains the values A B C C C D E and the search argument is D, then the last C will satisfy the search. If a descending array contains E D C C C B A and the search argument is D, then the first C will satisfy the search. If an entry lower than the search argument is not found in the array or table, the search is unsuccessful. 

**Eq -** Instructs the program to find the entry equal to the search argument. The first equal entry found sets the equal indicator on. If an entry equal to the search argument is not found, the search is unsuccessful.


### See Also
[%LOOKUP](LOOKUP_Function.html)

[%TLOOKUP](TLOOKUP_Function.html) 
