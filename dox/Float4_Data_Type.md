---
title: "*Float4 Data Type"

Id: Float4_Data_Type
TocParent: aerLrfDataTypesMain
TocOrder: 7


---

The * **Float4** data type defines a floating-point field of 4 bytes. The decimal positions must be left blank. However, floating-point fields are considered to have decimal positions. As a result, float variables may not be used in any place where a numeric value without decimal places is required, such as an array index, do loop index, etc. 

Use * **Float8** to specify a floating-point field of 8 bytes.

Negative values have the same range, but with a negative sign. 

***Float4** variables conform to the IEEE standard as supported by the AS/400. Since float variables are intended to represent "scientific" values, a numeric value stored in a float variable may not represent the exact same value as it would in a packed variable. Float should not be used when you need to represent numbers exactly to a specific number of decimal places, such as monetary amounts. 

The default initialization value for numeric fields is **zero.** 

The equivalent .NET data type is **System.Single.** 

### See Also
[Data Types](aerLrfDataTypesMain.html)

[*Float8](Float8_Data_Type.html) 
