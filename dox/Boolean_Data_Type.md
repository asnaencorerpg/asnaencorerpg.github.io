---
title: "*Boolean Data Type"

Id: Boolean_Data_Type
TocParent: aerLrfDataTypesMain
TocOrder: 1


---

The * **Boolean** data type is a special case of an [integer](Integer_Data_Type.html) data type. 

* **Boolean** data types are used with [*True](StarTRUE.html) or [*False](StarFalse.html) and can be used wherever indicators and character values "1" and "0" are used, such as with [DCLFLD](DCLFLD.html) and [DCLSRPARM](DCLSRPARM.html). 

**Character fields (*Char, *String).** 

If the contents are all "0" (character 0) then the character string converts to * **False** when assigned to a * **Boolean** . If one of the characters is not "0" then the character string maps to *True. Exception to this rule (or special case) is the empty *String, which maps to *False. 

**Numbers (*Packed, *Zoned, *Binary, *DECIMAL | *FLOAT, *Integer).** 

If all digits in the number equal 0 (i.e. if the number is 0) then it maps to * **False** , otherwise it maps to * **True** . 

**Indicators** 

Indicators are characters, so they follow the character fields rule.

The equivalent .NET data type is . 

### Example
Dclfld myBool type( *Boolean )<br /> myBool = *True<br /> myBool = *False 

### See Also
[Data Types](ecrLrfDataTypesMain.html)

[*True](StarTRUE.html)

[*False](StarFalse.html)

[DCLFLD](DCLFLD.html)

[Integer Data Type](Integer_Data_Type.html)

[DCLSRPARM](DCLSRPARM.html) 
