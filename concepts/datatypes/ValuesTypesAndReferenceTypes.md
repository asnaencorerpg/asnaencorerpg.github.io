---
title: Values Types and Reference Types

---

Although **value** types and **reference** types can be similar in terms of declaration syntax and usage, their semantics are distinct. 

**Reference** types are stored on the run-time heap; only being accessed through a reference to that storage. This allows the garbage collector to track outstanding references to a particular instance and free the instance when no references remain. A variable of **reference** type always contains a reference to a value of that type or a null reference. 

- A null reference refers to nothing; it is invalid to do anything with a null
                reference except assign it.
- Assignment to a variable of a **reference**  type creates a copy of
                the reference, not a copy of the value being referenced.

**Value** types are stored directly on the stack, either within an array or within another type. When the location containing a value type instance is destroyed, the value type instance is also destroyed. **Value** types are always accessed directly; it is not possible to create a reference to a value type. Prohibiting such a reference makes it impossible to refer to a value class instance that has been destroyed. A variable of a **value** type always contains a value of that type. 

Unlike **reference** types, the value of a **value** type cannot be a null reference, nor can it reference an object of a more derived type. Assignment to a variable of a value type creates a copy of the value being assigned. 

### Related Sections

[Value Types versus Reference Types](ValueTypesVsReferenceTypes.html)

Explains the difference between value and reference types, and which datatypes are which.


[DataTypes as 	Classes and Structures](DataTypesAsStructuresAndClasses.html)

Describes how Encore RPG datatypes are implemented in the underlying .NET 	Framework.


### See Also
[Language Concepts](/concepts/LanguageConceptsMain.html)

[DataTypes Main Topics](ecrLrfDataTypesMain.html)

[DataType Summary](Data_type_summary.html) 
