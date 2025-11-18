---
title: Data Type Summary

Id: Data_type_summary
TocParent: aerLrfDataTypesMain
TocOrder: 0


---

The following table shows the Encore RPG data types, their supporting common language runtime types, their nominal storage allocation, and their value ranges. 

| Encore RPG type | Common language runtime type structure | Nominal storage allocation | Value range |
| --- | --- | --- | --- |
| Boolean | [System.Boolean](https://learn.microsoft.com/dotnet/api/system.boolean) | 2 bytes | True or False. |
| Byte | [System.Byte](https://learn.microsoft.com/dotnet/api/system.byte) | 1 byte | 0 through 255 (unsigned). |
| Char | [System.Char](https://learn.microsoft.com/dotnet/api/system.char) | 2 bytes | 0 through 65535 (unsigned). |
| Date | [System.DateTime](https://learn.microsoft.com/dotnet/api/system.datetime) | 8 bytes | 0:00:00 on January 1, 0001 through 11:59:59 PM on December 31, 9999. |
| Decimal | [System.Decimal](https://learn.microsoft.com/dotnet/api/system.decimal) | 16 bytes | 0 through ±79,228,162,514,264,337,593,543,950,335 with no decimal point;<br/>0 through ±7.9228162514264337593543950335 with 28 places to the right of the decimal; smallest nonzero number is<br/>±0.0000000000000000000000000001 (±1E-28). |
| Integer | [System.Int32](https://learn.microsoft.com/dotnet/api/system.int32) | 4 bytes | -2,147,483,648 through 2,147,483,647. |
| Object | [System.Object](https://learn.microsoft.com/dotnet/api/system.object) (class) | 4 bytes | Any type can be stored in a variable of type Object. |
| String (variable-length) | [System.String](https://learn.microsoft.com/dotnet/api/system.string) (class) | Depends on implementing platform | 0 to approximately 2 billion Unicode characters. |


### Memory Consumption
When you declare an elementary data type, it is not safe to assume that its memory consumption is the same as its nominal storage allocation. The common language runtime assigns storage based on the characteristics of the platform on which your application is executing. In some circumstances it packs your declared elements as closely together as possible; in other cases it aligns their memory addresses to natural hardware boundaries. Also, storage assignment is different on a 64-bit platform than it is on a 32-bit platform. 

The same considerations apply to each member of a composite data type such as a structure or an array. Furthermore, some composite types have additional memory requirements. For example, an array uses extra memory for the array itself and also for each dimension. On a 32-bit platform, this overhead is currently 12 bytes plus 8 bytes for each dimension. On a 64-bit platform the requirement is doubled. You cannot rely on simply adding together the nominal storage allocations of the components. 

An **Object** referring to any elementary or composite data type uses 4 bytes in addition to the data contained in the data type. 

### See Also
[\*Byte Data Type](Byte_Data_Type.html)

[\*Char Data Type](Character_Data_Type.html)

[\*Date Data Type](Date_Data_Type.html)

[\*Integer Data Type](Integer_Data_Type.html)

[\*String Data Type](String_Data_Type.html)

[.NET Framework Data Types Comparison](/concepts/datatypes/FrameworkDataTypesComparison.html) 
