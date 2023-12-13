---
title: "%ELEM Function"

Id: ELEM_Function
TocParent: Functions_overview
TocOrder: 16


---

**%ELEM** [built-in function](Functions_overview.html) returns the number of elements in the specified array, table, or multiple-occurrence data structure. 

```
%ELEM (Table_name) 
 %ELEM (Array_name) 
 %ELEM (Multiple_occurrence_data_structure_name) 
```

### Parts

**Table_name, Array_name, Multiple_occurrence_data_structure_name** 

Required. The parameter must be the name of an array, table, or multiple occurrence data structure.


### Remarks
The value returned is in unsigned integer format (type U). It may be specified anywhere a numeric constant is allowed in the definition specification or in an expression in the extended Factor 2 field. 

The parameter must be the name of an array, table, or multiple occurrence data structure. 

The array must be declared using the [DCLARRAY](DCLARRAY.html) command to be supported by % **ELEM** . 

### See Also
[Built-in Function Overview](Functions_overview.html) 
