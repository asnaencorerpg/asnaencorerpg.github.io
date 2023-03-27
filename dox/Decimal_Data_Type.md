---
title: "*Decimal Data Type"

Id: Decimal_Data_Type
TocParent: aerLrfDataTypesMain
TocOrder: 5


---

The * **Decimal** data type variables are stored as signed 128-bit (16-byte) integers scaled by a variable power of 10. 

The scaling factor specifies the number of digits to the right of the decimal point; it ranges from 0 through 28. With a scale of 0 (no decimal places), the largest possible value is +/-79,228,162,514,264,337,593,543,950,335. With **28** decimal places, the largest value is +/-7.9228162514264337593543950335, and the smallest nonzero value is +/-0.0000000000000000000000000001 (+/-1E-28). 

The equivalent .NET data type is **System.Decimal** . 

### See Also
[Data Types](ecrLrfDataTypesMain.html) 
