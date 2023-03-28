---
title: BEGENUM

Id: BEGENUM
TocParent: aerLrfOpCodesMain
TocOrder: 60


---

Declares, or starts an enumeration definition. 

```
BEGENUM 
Name  (Enumeration name)
Access (<u>*PUBLIC</u> | *INTERNAL)
BaseType (Integral type name)
Attributes (Attribute 1, Attribute 2, ...)
```


### Parts

**Name** 

Required. The name of the enumeration definition.


**Access** 

Optional. Allows the enumeration definition to be accessible to the "outside world". *PUBLIC is the default. 

- *INTERNAL – enumeration definition is accessible by the whole assembly (all the classes in the same dll or exe).
- *PUBLIC (default) – enumeration definition is accessible by everybody.


**BaseType** 

Optional. If not given, it defaults to *Integer4. If given, it must be one of the integral types: *Integer2, *Byte, etc.


**Attributes** 

Optional. Allows you to list one or more attributes on the object being defined by the command. To specify more than one attribute, simply separate them with commas. 

Attributes use required, and optional arguments. The required parameters are provided in positional fashion. Positional arguments are arguments that are specified in the order they are declared for the constructor of an attribute. For example, the following code specifies the Developer attribute:<br /> 

```
BEGENUM MyClass Attributes(Developer("John Smith", 35))
```

Note &#8211; You must use positional arguments for arguments that are used with the
                attribute’s interface. Named arguments can only be used to set the values of
                fields and properties of attribute classes.


### Remarks
Enums are used to describe enumeration constants. Their only members are [DclEnumFld](DCLENUMFLD.html) fields. 

The **BEGENUM** routine must end with the [ENDENUM](ENDENUM.html) command. 

### Example

```
BegEnum  myEnum basetype(*byte) 
    DclEnumFld q4 (4)  // <--- the default value is 0
    DclEnumFld q5      // <--- this will be 5, which is 1 plus the previous one
EndEnum
```

### See Also
[ENDENUM](ENDENUM.html)

[DCLENUMFLD](DCLENUMFLD.html) 

[Enumeration Definition](ecrConEnumerationsOverview.html) 
