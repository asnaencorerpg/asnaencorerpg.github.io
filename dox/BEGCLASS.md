---
title: BEGCLASS

Id: BEGCLASS
TocParent: aerLrfOpCodesMain
TocOrder: 40


---

Declares a class, as well as a definition of the fields, properties, and methods that comprise the class.

```c
BEGCLASS
Name (ClassName)
Access (<u>*PUBLIC</u> | *INTERNAL)
Modifier (<u>*EXTENSIBLE</u>| *NOTEXTENSIBLE | *MUSTEXTEND)
Extends (ClassName)
Implements (interface1, interface2, ...)
Attributes (attribute1, attribute2, ...)
Partial (<u>*NO</u> | *YES)
DatEdit (<u>*DFT</u> | *YMD | *MDY | *DMY)
UsesCycle (<u>*NO</u> | *YES)
```

### Parameters

#### Name

Required. Defines a class.

#### Access

Optional. Allows the contents of the class to be accessed either only by other classes in the same assembly (exe or dll), or to classes in other assemblies. `*Public` is the default.

- `*Public` – class can be accessed from any other assembly.
- `*Internal` - class is accessible only by other classes in the current assembly.

#### Modifier

Optional. Modifier controls how properties and methods are overridden in derived classes. `*Extensible` is the default.

- `*Extensible` (default) - specifies that other classes can be defined to extend this class. The new class is called a *derived* class.
- `*MustExtend` - specifies that non-shared members of this class cannot be used on its own. The class only provides a set of fields, properties, and methods as the basis to derive new classes. nstances of *MustExtende classes cannot be created.
- `*NotExtensible` - specifies that this class cannot be extended in a new derived class. No further inheritance is allowed from this class.

#### Extends

Optional. Identifies the name of the base class to extend. The new class inherits all the visible members of the base class, and must implement any abstract member in the base class.

#### Implements

Optional. Indicates that this class implements an interface. An interface declares a set of properties and methods, but does not define them. The class must provide an implementation for all members of every interface specified here.

#### Attributes

Optional. Allows you to provide one or more attributes that apply to this class. To specify more than one attribute, simply separate them with commas.

#### Partial

Optional. Indicates if the class is partial, (that is, declared in parts); possibly in different source files. All the parts of a partial class must use Partial(`*Yes`). `*No` is the default.

#### DatEdit

Optional. Indicates the default date format in use for this class. If not given, the class uses the [project's default date format](/manuals/vs/projects/Config.html#default-datedit-format).

#### UsesCycle

### Remarks

A class declaration must end with an [EndClass](ENDCLASS.html) command, which must be the last command in the class.

For more information on classes, see topics within [Understanding Classes](/manuals/UnderstandingClassesMain.html).

For more information on attributes, see [Custom Attributes](/concepts/assemblies/CustomAttributes.html).

### Example

The following is an example of **BegClass**:

```c
Using System
Using ASNA.QSys.Runtime
Using ASNA.QSys.Runtime.JobSupport

BegClass CHECKDIGIT_Class Extends(Module) Access(*Public) +
  Attributes(System.ComponentModel.Description("Check if string has only digits"))

  DclFld Digits Type(*Char) Len(10) Inz("0123456789")
  DclFld JustDigits Type(*Ind)

  ...

EndClass
```

### See Also

[Custom Attributes](/concepts/assemblies/CustomAttributes.html)

[ENDCLASS](ENDCLASS.html)

[Understanding Classes](/manuals/UnderstandingClassesMain.html)
