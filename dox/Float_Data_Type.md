---
title: "*Float Data Type"

Id: Float_Data_Type
TocParent: aerLrfDataTypesMain
TocOrder: 6


---

The * **Float** data type defines a floating-point field. The decimal positions must be left blank. However, floating-point fields are considered to have decimal positions. As a result, float variables may not be used in any place where a numeric value without decimal places is required, such as an array index, do loop index, etc. 

The length of a floating-point field is defined in terms of the number of bytes. It must be specified as either 4 or 8 bytes. Use * **Float4** to set to 4 bytes and * **Float8** to set to 8 bytes. 

Negative values have the same range, but with a negative sign. 

***Float** variables conform to the IEEE standard as supported by the AS/400. Since float variables are intended to represent "scientific" values, a numeric value stored in a float variable may not represent the exact same value as it would in a packed variable. Float should not be used when you need to represent numbers exactly to a specific number of decimal places, such as monetary amounts. 

The default initialization value for numeric fields is **zero.** 

### See Also
[Data Types](ecrLrfDataTypesMain.html)

[*Float4](Float8_Data_Type.html)

[*Float8](Float8_Data_Type.html) 
