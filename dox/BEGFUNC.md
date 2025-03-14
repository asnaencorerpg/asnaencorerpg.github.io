---
title: BEGFUNC

Id: BEGFUNC
TocParent: aerLrfOpCodesMain
TocOrder: 70


---

Defines a function, which is a method that returns a value.

```c
BEGFUNC 
Name  (Function name) 
Type  (*BOOLEAN | *BINARY | *BYTE | *CHAR | *DATE | *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 | *IND | *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *OBJECT | *PACKED | *STRING | *TIME | *TIMESTAMP | *ZONED | name | Library.Object) 
Len (Length, [Decimal Positions]) 
TimFmt (*<u>PGMDFT</u> | *MDY | *DMY | *YMD | *JUL | *ISO | *USA | *EUR | *JIS | *HMS)
Rank (Integer)
Shared (<u>*NO</u> | *YES) 
Access (<u>*PRIVATE</u> | *INTERNAL | *PUBLIC |*PROTECTED) 
Modifier (<u>*NONE</u> | *MUSTOVERRIDE | *NOTOVERRIDABLE | *OVERRIDABLE | *OVERRIDES) 
Implements (Interface1 [, interface2, ...]) 
Attributes (attribute1 [, attribute2, ...])
Like (Name)
ReturnAttributes (attribute1 [, attribute2, ...])
```

### Parameters

#### Name

Required. The name of the function. The same name can be shared among several subroutines or functions as long as they differ in the number and/or type of arguments they receive.

#### Type

Optional. Declares the return type of the function. `Type` can be any of the Encore predefined types, or the name of a class. See [Type Parameter](Type_Parameter.html) for further information.

If a **Type** parameter is not given, it will default to `*Zoned` for a **Len** with two arguments, or `*Char` for a **Len** with one argument.

#### Len

Optional. **Len** is required depending on the **Type** parameter, usually when it is one of the Encore RPG fixed-size types. **Type** is optional when declaring a `*Zoned` or a `*Char` field.

#### TimFmt

Optional. If the **Type** refers to one of the date/time types of Encore RPG, **TimFmt** specifies its format, either [time](Time_Formats.html), [date](Date_Formats.html), or [timestamp](Timestamp_Data_Type.html). If the **TimFmt** parameter is not specified, the default format for the class or the assembly will be used.

#### Rank

Optional. **Rank** is used when the funtion returns an array. The value given defines the number of dimensions for the array.

#### Shared

Optional. Declares whether the function is a *class* (or *static*) function or an *instance* function. `*NO` is the default.

- `*NO` (default) - declares an *instance* funtion, that has access to the instance and static members of a class.
- `*YES` - declares a *static* function, not associated with an object but with the class itself. It has access only to the static members of the class.

#### Access

Optional. Declares who can call this function. `*PRIVATE` is the default.

- `*PRIVATE` (default) - the function is accessible only from the current class.
- `*INTERNAL` - the function is accessible in the current assembly, i.e. all the classes in the same dll or exe.
- `*PUBLIC` - the function is accessible by everybody.
- `*PROTECTED` - the function is accessible only by the current class and classes that extend the current class.

#### Modifier

Optional. Modifier controls how properties and methods are overridden in derived classes. *NONE is the default.

- *NONE (default) - specifies that none of the override options are available for properties and methods.
- *MUSTOVERRIDE - specifies that a property or procedure in a base class must be overridden in a derived class before it can be used.
- *NOTOVERRIDABLE - specifies that a property or procedure cannot be overridden in a derived class.
- *OVERRIDABLE - specifies that a property or method can be overridden in a derived class.
- *OVERRIDES - specifies that a property or method overrides a member inherited from a base class.

#### Implements

Optional. Indicates that this class implements the members of an interface. An interface defines a set of properties and methods, but does not provide an implementation of them, just a declaration. You must implement every member of every interface you specify in this keyword.

#### Attributes

Optional. Allows you to provide one or more attributes that apply to this class. To specify more than one attribute, simply separate them with commas.

#### Like

Optional. **Like** must be the name of a field already defined in the class. Declares that the return type of this function is the same as the type of the field referenced in the **Like** parameter. For fixed-length Encore RPG types, those requiring a **Len** parameter, the length can be modified when using **Like** by the use of **Len**. A positive number in **Len** indicates an *increase* in the total length of the type by that amount. A negative number indicates a *decrease* by that amount.

#### ReturnAttributes

Optional. Allows you to give attributes to the return value of the **BegFunc**.

### Remarks

A **BegFunc** routine must always contain a [LEAVESR](LEAVESR.html) and end with an [ENDFUNC](ENDFUNC.html), as shown in the example below.

### Example

```c
BegFunc MyFunc Type(*IND) Access (*PUBLIC)
    Chain CustMaster CustNumber NotFnd(*IN60)
    LeaveSr *IN60
EndFunc
```

#### See Also

[BEGPROP](BEGPROP.html)

[BEGSR](BEGSR.html)

[Custom Attributes](/concepts/assemblies/CustomAttributes.html)

[DCLSRPARM](DCLSRPARM.html)

[ENDFUNC](ENDFUNC.html)

[LEAVESR](LEAVESR.html)
