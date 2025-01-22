---
title: "*Char Data Type"

Id: Character_Data_Type
TocParent: aerConElementaryDataTypes
TocOrder: 1


---

The * **Char** data type is a finite-length string of Unicode text characters that compose an RPG field. Internally, this field is characterized as a string, but, as a field, the length of the string is always the exact length of the * **Char** field definition. 

**For example:** 

```
dclFld CustName type( *char )    Len( 35 ) 
dclFld myStr    type( *string )
myStr = CustName.Trim()     // trim white space
```

### See Also
[Data Types](ecrLrfDataTypesMain.html)

[Unicode](ecrConUnicode.html) 
