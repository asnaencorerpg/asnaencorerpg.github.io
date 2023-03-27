---
title: BEGCLASS

Id: BEGCLASS
TocParent: aerLrfOpCodesMain
TocOrder: 40


---

Declares the name of a class, as well as a definition of the variables, properties, events and methods that comprise the class. 

```
 **BEGCLASS
Name** (Class name)
Partial (<u>*NO</u>  | *YES)
Access(<u>*PUBLIC</u> | *INTERNAL)
Modifier (<u>*EXTENSIBLE</u>| *NOTEXTENSIBLE | *MUSTEXTEND)
Extends (Class name)
Implements (Interface name list)
Attributes (attribute 1, attribute 2, ...)
```

### Parts

**Name** 

Required. Contains the name of the class.


**Partial** 

Optional. Indicates if the class is partial, (that is, declared in parts); possibly in different source files. All the parts of a partial class must use Partial(*YES). *NO is the default.


**Access** 

Optional. Allows the contents of the class to be access either only internally by other class in the same assembly (exe or dll), or to the "outside world". *Public is the default. 

- *PUBLIC – class is accessible to the "outside" world, that is, it can be referenced by any other assembly.
- *INTERNAL - class is accessible only by other classes in the current assembly.


**Modifier** 

Optional. Modifier controls how properties and methods are overridden in derived classes. *EXTENSIBLE is the default. 

- *EXTENSIBLE (default) - specifies that other classes can be defined to extend this class. The new class is called a derived class.
- *MUSTEXTENDED - specifies that non-shared members of this class cannot be used on its own. The class only provides a set of fields, properties, events and methods as the basis to derive new classes. nstances of *MustExtende classes cannot be created.
- *NOTEXTENSIBLE - specifies that this class cannot be extended in a new derived class. No further inheritance is allowed from this class.


**Extends** 

Optional. Identifies the name of the base class to extend, such as System.Windows.Forms.Form. The new class inherits all the members of the base class.


**Implements** 

Optional. Indicates that this class implements the members of an interface. An interface defines a set of properties, events and methods, but does not provide an implementation of them, just a definition. You must implement every member of every interface you specify in this keyword.


**Attributes** 

Optional. Allows you to provide one or more attributes that apply to this class. To specify more than one attribute, simply separate them with commas.


### Remarks
An [ENDCLASS](ENDCLASS.html) statement must be the last statement in the class. 

For more information on classes, see topics within [Understanding Classes](aerTourUnderstandingClassesMain.html). 

For more information on attributes, see [Custom Attributes](aerConCustomAttributes.html). 

### Example
The following is an example of **BEGCLASS** showing attribute usage: 

```
Using System.ComponentModel
Using System.Reflection 
BEGCLASS Boxer Extends(System.Windows.Forms.TextBox) + 
Attributes(DefaultProperty("myValue") +
Description("With two custom attributes"))

  DclFld AnInt  Type( *Integer) Len(4) Attributes(DefaultValue(85))
  DclFld AStr   Type( *String)         Attributes(DefaultValue("Jupiter"))
  DclFld XColor Type(*Integer)  Len(4) Access(*Public) +

Attributes (Description("Radix showing color"),+
Category("Appearance"))
ENDCLASS
```

### See Also
[Custom Attributes](aerConCustomAttributes.html)

[ENDCLASS](ENDCLASS.html)

[Understanding Classes](aerTourUnderstandingClassesMain.html) 
