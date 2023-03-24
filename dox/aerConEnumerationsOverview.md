---
title: Enumerations Overview

Id: aerConEnumerationsOverview
TocParent: aerConLanguageConceptsMain
TocOrder: 5


---

Enumerations provide a convenient way to work with sets of related constants and to associate constant values with names. For example, you can declare an enumeration for a set of integer constants associated with the days of the week, and then use the names of the days rather than their integer values in your code. 

You create an enumeration in the declarations section of a class or module, using the **DclEnumFld** op code. 

A **DclEnumFld** type has a name, an underlying type, and a set of fields, each representing a constant. The name must be a valid Encore RPG for Visual Studio qualifier. The underlying type must be one of the integer types — ***Byte** , ***Integer2,** etc. * **Integer4** is the default. Enumerations are always strongly typed and are not interchangeable with integer number types. 

You can assign the same value to multiple fields. When you do so, the compiler marks one of the **Enum** values as primary for purposes of string conversion and reflection. You can use an assignment statement to explicitly assign values to constants in an enumeration. All integer values, including negative numbers, are permissible. 

### See Also
[BEGENUM](BEGENUM.html)
[DCLENUMFLD](DCLENUMFLD.html)
[ENDENUM](ENDENUM.html) 
