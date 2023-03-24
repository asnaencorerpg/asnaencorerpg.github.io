---
title: Value Types vs. Reference Types

Id: aerConValueTypesvsReferenceTypes
TocParent: aerConDataTypeImplementation
TocOrder: 1


---

ECR references **value types** and **reference types** .

**Value** types include simple types (e.g., char, int, and float), enum types, and structure types. Reference types include class types, interface types, delegate types, and array types. Value types differ from reference types in that variables of the value types directly contain their data, whereas variables of the reference types store references to objects. 

With **reference** types, it is possible for two variables to reference the same object, and thus possible for operations on one variable to affect the object referenced by the other variable. With value types, the variables each have their own copy of the data, and it is not possible for operations on one to affect the other. 

In ECR, pretty much all types (```*<something>```) are value types, **except:** ```*object, *string, *form```, and as of 7.1 enumerations (```BegEnum```). 

- Fields declared with a **value** 
                type have a default value which depends on the particular type (like 0 for
                numerics or blanks for ```*char```).
- Fields declared with a **reference**  type all have the same
                default value which is ```*Nothing```. 
                <br /> ** *Therefore they must be initialized before they can be used* .** 
                You can test for ```*nothing``` in conditional expressions (eg. ```
                    IF (mystring =
                    *nothing
                ```) ...)

### Related Sections

[Value Types and Reference Types](aerConValuesTypesandReferenceTypes.html)

Explains the difference between value and reference types in terms of
                declaration syntax, usage, and semantics.


[DataTypes as Classes and Structures](aerConDataTypesasStructuresandClasses.html)

Describes how Encore RPG datatypes are implemented in the underlying .NET Framework.


### See Also
[Language Concepts](aerConLanguageConceptsMain.html)
[DataTypes Main Topics](aerLrfDataTypesMain.html)
[DataType Summary](Data_type_summary.html) 
