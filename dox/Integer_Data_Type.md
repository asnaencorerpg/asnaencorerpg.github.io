---
title: "*Integer Data Type"

Id: Integer_Data_Type
TocParent: aerLrfDataTypesMain
TocOrder: 11


---

The * **Integer** data type is similar to * **Binary** , with these exceptions: 

- The integer format allows the full range of binary values.
- The number of decimal positions for an integer field is always zero.
- Its length is defined in bytes, rather than digits.

The length of an integer field is defined in terms of number of bytes; it can be either 2 or 4 byes long. The range of values allowed for an integer field depends on its length. 

**Field Length Range of Allowed Values** 

**2-byte integer** 

-32768 to 32767 

**4-byte integer** 

-2147483648 to 2147483647 

The equivalent .NET data type is **System.Int32** .

You can also use the following data types to automatically set the length of the data type. 

* **Integer2** - sets the length to a 2-byte integer.

* **Integer4** - sets the length to a 4-byte integer.

* **Integer8** - sets the length to an 8-byte integer.

### See Also
[Data Types](ecrLrfDataTypesMain.html)

[*Integer2](Integer2_data_type.html)

[*Integer4](Integer4_Data_Type.html)

[*Integer8](Integer8_Data_Type.html) 
