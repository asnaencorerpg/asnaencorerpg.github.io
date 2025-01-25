---
title: BEGENUM

Id: BEGENUM
TocParent: aerLrfOpCodesMain
TocOrder: 60


---

Begins an enumeration definition.

```c
BEGENUM 
Name (Enumeration name)
Access (<u>*PUBLIC</u> | *INTERNAL)
BaseType (Integral type name)
Attributes (Attribute 1, Attribute 2, ...)
```

### Parameters

#### Name

Required. The name of the enumeration definition.

#### Access

Optional. Defines the accessibility of the enumeration:

- `*INTERNAL` – enumeration definition is accessible by the current assembly (all the classes in the same dll or exe).
- `*PUBLIC` (default) – enumeration definition is accessible outside of the current assembly.

#### BaseType

Optional. Declares the base type for the values in this enumeration. It defaults to `*Integer4`. If given, it must be one of the integral types: `*Integer2`, `*Byte`, etc.

#### Attributes

Optional. Allows you to list one or more attributes on the enumeration. To specify more than one attribute, simply separate them with commas.

Example:

```c
BegEnum SevenDwarves Attributes(Description("Enumeration of Snow White's 7 dwarf friends"))
```

**Note &#8211;** You must provide all arguments that are defined in the attribute's constructor. Use named arguments to set the values of properties in the attribute class.

### Remarks

Enums are used to describe enumeration constants. Their only members are [DclEnumFld](DCLENUMFLD.html) fields.

A `BegEnum` block must end with an [`EndEnum`](ENDENUM.html) command.

### Example

```c
BegEnum  myEnum basetype(*byte) 
    DclEnumFld q4 (4)  // <--- the default value is 0
    DclEnumFld q5      // <--- this will be 5, which is 1 plus the previous one
EndEnum
```

### See Also

[ENDENUM](ENDENUM.html)

[DCLENUMFLD](DCLENUMFLD.html)

[Enumeration Definition](ecrConEnumerationsOverview.html)
