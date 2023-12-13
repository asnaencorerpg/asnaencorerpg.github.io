---
title: "%SIZE Function"

Id: SIZE_Function
TocParent: Functions_overview
TocOrder: 40


---

**%SIZE** [built-in function](Functions_overview.html) returns the number of bytes occupied by the constant or field, or the number of digits of *Binary fields. The argument may be a literal, a named constant, a data structure, a data structure subfield, a field, an array or a table name. It cannot, however, contain an expression. 

```
%Size (argument | *ALL )
```

### Parts

** *Argument* ** 

Required. Must be a literal, named constant, data structure, data structure subfield, field, array or table name. It cannot, however, contain an expression. The value returned is in unsigned integer format.


### Remarks

- Use % **Size** to return the correct size of * **Binary** fields in ECR, since the size of * **Binary** fields is its number of Digits (like *Zoned); as shown in the example below.

<pre>  DCLFLD myBinary *Binary (8,0)
 %Size (myBinary)             // returns 8       </pre>

### See Also
[Built-in Function Overview](Functions_overview.html) 
