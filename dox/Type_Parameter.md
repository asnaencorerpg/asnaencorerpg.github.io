---
title: Type Parameter

Id: Type_Parameter
TocParent: aerLrfDataTypesMain
TocOrder: 50


---

The **Type** Parameter can be any of the "*" [Data Types](ecrLrfDataTypesMain.html) (*CHAR, *BINARY, etc.) as listed below, or it can be the name of a field already defined in the program. 

- Type cannot be a named constant or a literal. In this case, the field will be defined based on the attributes of another field.

- Type can be a **Name** , where **Name** is a variable that has already been defined.
- Type can be a **string literal** , which defines an *OBJECT variable of a particular type. The string literal must represent: 
<ul>
                    <li>

a valid program id registered on your system at compile time
- a valid class id registered on your system at compile time.
- a valid interface name registered on your system at compile time.

</li>
            <li>

Type can be a name of the form **Library.Object** ; where **Library** is the name of one of the libraries selected in the object libraries dialog, and **Object** is a valid object name within that library. 
</li>
            <li>

Type can be an array, array element, or a table name. The attributes of an element of the array or the table are used to define the field. 
</li>
            <li>

If **Type** is *BOOLEAN, you can use the *TRUE or *ON and *FALSE or *OFF special values to indicate True or False. 
</li>
            <li>

If a **Type Parameter** is not given, the **Len** parameter is required. In this case, *CHAR is assumed if there is one integer, and *ZONED is assumed if there are two integers. The length of an ***INTEGER** Type is 2- or 4-bytes. The length of a * **FLOAT** Type is 4- or 8-bytes.<br /> 
</li>
        </ul>

#### Supported Data Types:
[*BINARY](Binary_Data_Type.html) 

[*BOOLEAN](Boolean_Data_Type.html) 

[*BYTE](Byte_Data_Type.html) 

[*CHAR](Character_Data_Type.html) 

[*DATE](Date_Data_Type.html) 

[*DECIMAL](Decimal_Data_Type.html) 

[*FLOAT](Float_Data_Type.html) 

[*IND](Ind_Data_Type.html) 

[*INTEGER](Integer_Data_Type.html) 

[*ONECHAR](Onechar_Data_Type.html) 

[*PACKED](Packed_Data_Type.html) 

[*STRING](String_Data_Type.html) 

[*TIME](Time_Data_Type.html) 

[*TIMESTAMP](Timestamp_Data_Type.html) 

[*ZONED](Zoned_Data_Type.html) 

### See Also
[Data Types](ecrLrfDataTypesMain.html) 
