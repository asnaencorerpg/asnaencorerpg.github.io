---
title: BEGSR

Id: BEGSR
TocParent: aerLrfOpCodesMain
TocOrder: 140


---

Defines a subroutine, which is a method that does not return values.

```c
BEGSR 
Name (Subroutine name)
Shared (<u>*NO</u> | *YES) 
Access (<u>*PRIVATE</u> | *INTERNAL | *PUBLIC |*PROTECTED) 
Modifier (<u>*NONE</u> | *MUSTOVERRIDE | *NOTOVERRIDABLE | *OVERRIDABLE | *OVERRIDES) 
Implements (Interface1 [, interface2, ...]) 
Attributes (attribute1 [, attribute2, ...])
```

For subroutines nested within procedures:

```c
BEGSR 
Name  (Function name | *PSSR )
ExName (field name) //use only when Name(*PSSR) is used
```

### Parameters

#### Name

Required. The name of the subroutine. This is the name to be used on an [EXSR](EXSR.html) operation to call the subroutine. The same name can be shared among several subroutines or functions as long as they differ in the number and/or type of arguments they receive.

Names for nested subroutines ***must*** be unique, as nested subroutines do not take arguments. Nested subroutines also allow the special name `*PSSR`, which defines the subroutine as the subroutine from RPG that handles program exceptions. If `*PSSR` is used, then you must also use the parameter **ExName**, which declares the field name that contains the exception trapped by the `*PSSR` subroutine.

#### Shared

Optional. Declares whether the subroutine is a class subroutine or an instance subroutine. `*NO` is the default.

- `*NO` (default) - declares an *instance* subroutine, used to initialize an instance (that is, an object) of a class.
- `*YES` - declares a *class* subroutine, not associated with an object but with the class itself. A class subroutine must not define parameters.

#### Access

Optional. Defines who can call this subroutine. `*PRIVATE` is the default.

- `*PRIVATE` (default) - the subroutine is accessible only from the current class.
- `*INTERNAL` - the subroutine is accessible in the current assembly, i.e. all the classes in the same dll or exe.
- `*PUBLIC` - the subroutine is accessible by everybody.
- `*PROTECTED` - the subroutine is accessible only by the current class and classes that extend the current class.

#### Modifier

Optional. The type of access to the property. The default is *PRIVATE.

- *MUSTOVERRIDE - specifies that a property or procedure in a base class must be overridden in a derived class before it can be used.
- *NOTOVERRIDABLE - specifies that a property or procedure cannot be overridden in a derived class.
- *OVERRIDABLE - specifies that a property or method can be overridden in a derived class.
- *OVERRIDES - specifies that a property or method overrides a member inherited from a base class.

#### Implements

Optional. Indicates the interface member that this subroutine implements.

#### Attributes

Optional. Allows you to provide one or more attributes that apply to this subroutine. To specify more than one attribute, simply separate them with commas.

Example:

```c
BegSr Main Shared(*Yes) Access(*Public) Attributes(System.STAThread())
    DclSrParm args Type(*String) Rank(1)

EndSr
```

#### ExName

Optional. This parameter **must only** be used in a nested subroutine if its name is `*PSSR`. **ExName** declares the field name that contains the exception trapped by the `*PSSR` subroutine.

### Remarks

There are two kinds of subroutines:

- Subroutines that are members of the class, similar to a  **BegFunc**.
- Subroutines nested within procedures and subprocedures.

#### For subroutines that are class members

Parameters may be declared by using **DclSrParm** commands right after the **BegSr** . See [DCLSRPARM](DCLSRPARM.html) for more information.

[**EndSr**](ENDSR.html) must be the last statement in the subroutine.

#### For nested subroutines

Nested subroutines only have two parameters: **Name** and **ExName**.

- **Name** (Required) - identifies the name of the procedure. It can be either a valid Encore RPG identifier or the special value `*PSSR`.
- **ExName** - this parameter **must only** be used if the name of the nested subroutine is `*PSSR`. **ExName** declares the field name that contains the exception trapped by the `*PSSR` subroutine.

### Example

```c
BegSr MyFunc Access (*PUBLIC)
    Chain CustMaster CustNumber NotFnd(*IN60)
    If *IN60
        LeaveSr
    EndIf
    // work with the record that was read
    ...
    // LeaveSr not needed if it's the last statement in the subroutine
EndSr
```

### See Also

[Built-In Controls](Control_Properties.html)

[BEGFUNC](BEGFUNC.html)

[BEGPROC](BEGPROC.html)

[Custom Attributes](ecrConCustomAttributes.html)

[DCLSRPARM](DCLSRPARM.html)

[ENDSR](ENDSR.html)

[EXSR](EXSR.html)
