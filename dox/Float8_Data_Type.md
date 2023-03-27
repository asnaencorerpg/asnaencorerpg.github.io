---
title: "*Float8 Data Type"

Id: Float8_Data_Type
TocParent: aerLrfDataTypesMain
TocOrder: 8


---

The * **Float8** data type defines a floating-point field to 8 bytes. The decimal positions must be left blank. However, floating-point fields are considered to have decimal positions. As a result, float variables may not be used in any place where a numeric value without decimal places is required, such as an array index, do loop index, etc. 

Use * **Float4** to specify a floating-point field to 4 bytes.

Negative values have the same range, but with a negative sign. 

***Float8** variables conform to the IEEE standard as supported by the AS/400. Since float variables are intended to represent "scientific" values, a numeric value stored in a float variable may not represent the exact same value as it would in a packed variable. Float should not be used when you need to represent numbers exactly to a specific number of decimal places, such as monetary amounts. 

The default initialization value for numeric fields is **zero.** 

The equivalent .NET data type is **System.Double.** 

### See Also
[Data Types](ecrLrfDataTypesMain.html)

[*Float4](Float8_Data_Type.html) 
