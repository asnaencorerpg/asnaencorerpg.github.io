---
title: DataType Comparison

Id: aerConFrameworkDataTypesComparison
TocParent: aerConDataTypes
TocOrder: 3


---

The following table shows the Encore RPG data types, their supporting .NET framework type, and the equivalent C# data type. They are listed by hierarchical view of data types. Additional information can be found in the Encore RPG Language Reference links within the table and the 'Related Sections" and "See Also" below. 


| Encore RPG type                               | .NET Type                                                                                | C# Type
| --------------------------------------------- | ---------------------------------------------------------------------------------------- | --------
| **REFERENCE TYPES:**                          |                                                                                          |
| [*String](String_Data_Type.html)              | [System.String](https://learn.microsoft.com/en-us/dotnet/api/system.string)              | string
| [*Char](Character_Data_Type.html)             | [System.String](https://learn.microsoft.com/en-us/dotnet/api/system.string)              | N/A
| [*Object](/concepts/objects/Objects.html)     | [System.Object](https://learn.microsoft.com/en-us/dotnet/api/system.object)              | object
| **VALUE TYPES:**                              |                                                                                          |
| *Structure Types* :                           |                                                                                          |
| [*Date](Date_Data_Type.html)                  | [System.DateTime](https://learn.microsoft.com/en-us/dotnet/api/system.datetime)          | datetime
| [*Time](Time_Data_Type.html)                  | [System.DateTime](https://learn.microsoft.com/en-us/dotnet/api/system.datetime)          | datetime
| [*TimeStamp](Timestamp_Data_Type.html)        | [System.DateTime](https://learn.microsoft.com/en-us/dotnet/api/system.datetime)          | datetime
| *Simple Types* :                              |                                                                                          |
| Logical:                                      |                                                                                          |
| [*Boolean](Boolean_Data_Type.html)            | [System.Boolean](https://learn.microsoft.com/en-us/dotnet/api/system.boolean)            | bool
| [*Ind](Ind_Data_Type.html)                    | [System.Char](https://learn.microsoft.com/en-us/dotnet/api/system.char)                  | N/A
| Numeric Decimal:                              |                                                                                          |
| [*Binary](Binary_Data_Type.html)              | [System.Decimal](https://learn.microsoft.com/en-us/dotnet/api/system.decimal)            | N/A
| [*Deciaml](Decimal_Data_Type.html)            | [System.Decimal](https://learn.microsoft.com/en-us/dotnet/api/system.decimal)            | decimal
| [*Packed](Packed_Data_Type.html)              | [System.Decimal](https://learn.microsoft.com/en-us/dotnet/api/system.decimal)            | N/A
| [*Zoned](Zoned_Data_Type.html)                | [System.Decimal](https://learn.microsoft.com/en-us/dotnet/api/system.decimal)            | N/A
| Numeric Floating Point:                       |                                                                                          |
| [*Float4](Float4_Data_Type.html)              | [System.Single](https://learn.microsoft.com/en-us/dotnet/api/system.single)              | float
| [*Float8](Float8_Data_Type.html)              | [System.Double](https://learn.microsoft.com/en-us/dotnet/api/system.single)              | double
| Numeric Integral:                             |                                                                                          |
| [*Byte](Byte_Data_Type.html)                  | [System.Byte](https://learn.microsoft.com/en-us/dotnet/api/system.byte)                  | byte
| [*Integer2](Integer2_Data_Type.html)          | [System.Byte](https://learn.microsoft.com/en-us/dotnet/api/system.int16)                 | short
| [*Integer4](Integer4_Data_Type.html)          | [System.Byte](https://learn.microsoft.com/en-us/dotnet/api/system.int32)                 | int
| [*Integer8](Integer8_Data_Type.html)          | [System.Byte](https://learn.microsoft.com/en-us/dotnet/api/system.int64)                 | long
| Character:                                    |                                                                                          |
| [*OneChar](OneChar_Data_Type.html)            | [System.Char](https://learn.microsoft.com/en-us/dotnet/api/system.char)                  | char


### Remarks
To be completely precise, all values types are structures derived from System.Value. The distinction this chart draws between *Structure Types* and *Simple Types* is that simple types focus on providing one data element (their value), whereas the date/time structures provide several data elements as sub elements of the date/time values. 

### Related Sections
[Data Type Declaration](DataTypeDeclaration.html) <br /> 
Covers declaring data types of various programming elements. 

[Elementary Data types](ElementaryDataTypes.html) <br />
Discusses numeric, character, and miscellaneous types provided by Encore RPG. 

[Data type Implementation](DataTypeImplementation.html) <br />
Illustrates how Encore RPG classifies and implements various data types. 

### See Also
[Language Concepts](/concepts/LanguageConceptsMain.html)

[Data type Summary](Data_type_summary.html)

[Type Conversions](Type_Conversions.html)

[*Float Data type](Float_Data_Type.html)

[*Integer Data type](Integer_Data_Type.html) 
