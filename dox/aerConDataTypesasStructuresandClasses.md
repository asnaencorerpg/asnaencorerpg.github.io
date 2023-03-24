---
title: DataTypes as Classes and Structures

Id: aerConDataTypesasStructuresandClasses
TocParent: aerConDataTypeImplementation
TocOrder: 2


---

Every elementary data type in Encore RPG is supported by a structure or a class in the ```System``` namespace. The compiler uses each data type keyword as an alias for the underlying structure or class. For example, declaring a variable with the reserved word ```Byte``` is the same as declaring it with the fully qualified structure name ```System.Byte```. 

In the .NET Framework, a structure is a value type and a class is a reference type. For this reason, value types such as ```*Char``` and ```*Integer``` are supported by .NET structures, while reference types such as ```*Object``` and ```*String``` are supported by .NET classes. 

Since every reference type represents an underlying .NET class, you must use the ```*New``` special value when you initialize it. 

You can also use the ```*New``` special value to initialize a value type. This is particularly useful if the type has a constructor that takes parameters. 

### Related Sections

[Value Types and Reference Types](aerConValuesTypesandReferenceTypes.html)

Explains the difference between value and reference types in terms of
                declaration syntax, usage, and semantics.


[Value Types versus Reference Types](aerConValueTypesvsReferenceTypes.html)

Explains the difference between value and reference types, and which data
                types 	are which.


### See Also
[Language Concepts](aerConLanguageConceptsMain.html)
[Data types Main Topics](aerLrfDataTypesMain.html)
[Data type Summary](Data_type_summary.html) 
