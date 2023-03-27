---
title: BEGINTERFACE

Id: BEGINTERFACE
TocParent: aerLrfOpCodesMain
TocOrder: 90


---

Declares, or starts an interface definition. 

```
 **BEGINTERFACE** 
 **Name**  (Interface name)
Access (<u>*PUBLIC</u> | *INTERNAL)
Implements (Interface name list)
Attributes (Attribute 1, Attribute 2, ...)
```

### Parts

**Name** 

Required. The name of the interface definition.


**Access** 

Optional. Allows the interface definition to be accessible to the "outside world". *PUBLIC is the default. 

- *INTERNAL – interface definition is accessible by the whole
                        assembly (all the classes in the same dll or exe).
- *PUBLIC (default) – interface definition is accessible by everybody.


**Implements** 

Optional. Indicates that this class implements the members of an interface. An interface defines a set of properties, events and methods, but does not provide an implementation of them, just a definition. You must implement every member of every interface you specify in this keyword.


**Attributes** 

Optional. Allows you to list one or more attributes on the object being defined by the command. To specify more than one attribute, simply separate them with commas.


Attributes use required, and optional arguments. The required parameters are provided in positional fashion. Positional arguments are arguments that are specified in the order they are declared for the constructor of an attribute. For example, the following code specifies the Developer attribute: 

```
BEGINTERFACE MyClass Attributes(Developer("John Smith", 35))
```

**Note &#8211;** You must use positional arguments for arguments that are used with the attribute’s interface. Named arguments can only be used to set the values of fields and properties of attribute classes.


### Remarks
Interfaces can only contain methods (functions and subroutines), properties, and TYPE-declared events. Fields and PARM-declared events are not allowed. In addition to this, the interface methods (including properties' get-and set-methods) must not have a body. 

Interface members must not define their Access, Modifier and Shared keywords, as they are *Public, *MustOverride, and Shared (*No) by default. 

In keeping with standard practice, we recommend interface names to begin with a capital letter "I", i.e., IDisposable, IEnumerable, etc. See "Design Guidelines for Class Library Developers" in the Documentation. 

The **BEGINTERFACE** routine must end with the [ENDINTERFACE](ENDINTERFACE.html) command. 

### Example

```
 //Define an Interface BegInterface **myInterface** 
  BegSr Customer
    DclSrParm Name *integer4
  EndSr

  BegFunc Function Type( *integer4 )
  EndFunc
  DclEvent EVENT type( System.EventHandler )
EndInterface

 // Interface Usage BegClass Overloaded Access (*Public) Implements( **myInterface**  )
  BegSr First Access (*Public) implements ( myInterface.Customer )
    DclSrParm theParm *interger4
  EndSr
```

### See Also
[ENDINTERFACE](ENDINTERFACE.html)

[Interface Definition](ecrConInterface.html) 
