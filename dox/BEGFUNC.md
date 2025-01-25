---
title: BEGFUNC

Id: BEGFUNC
TocParent: aerLrfOpCodesMain
TocOrder: 70


---

Declares a function, which is a method that has a return value.

```c
BEGFUNC 
Name  (Function name) 
Type  (*BOOLEAN | *BINARY | *BYTE | *CHAR | *DATE | *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 | *IND | *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *OBJECT | *PACKED | *STRING | *TIME | *TIMESTAMP | *ZONED | name | String Literal | Library.Object) 
Len (Length, [Decimal Positions]) 
TimFmt (*<u>PGMDFT</u> | *MDY | *DMY | *YMD | *JUL | *ISO | *USA | *EUR | *JIS | *HMS)
Rank (Integer)
Shared (<u>*NO</u> | *YES) 
Access (<u>*PRIVATE</u> | *INTERNAL | *PUBLIC |*PROTECTED) 
Modifier (<u>*NONE</u> | *MUSTOVERRIDE | *NOTOVERRIDABLE | *OVERRIDABLE | *OVERRIDES) 
Implements (Interface1 [, interface2, ...]) 
Attributes (attribute1 [], attribute2, ...])
Like (Name)
Event (<u>*NONE</u> | *CHANGE | event name)
ReturnAttributes (attribute1 [, attribute2, ...])
```

### Parameters

#### Name

Required. The name of the function.

#### Type

Required. Defines the return type of the function. `Type` can be any of the Encore predefined types, or the name of a class. See [Type Parameter](Type_Parameter.html) for further information.

- **Name** is the name of the variable already defined.
- A string literal, which defines an *OBJECT variable of a particular type. The string literal must represent:

- a valid program id registered on your system at compile time.
- a valid class id registered on your system at compile time.
- a valid interface name registered on your system at compile time.
- A name of the form Library.Object, where Library is the name of one of the libraries selected in the new up and coming object libraries dialog, and Object is valid object name within that library.

If a **Type** parameter is not given, the **Len** parameter is required. In this case, *CHAR is assumed if there is one integer, and *ZONED is assumed if there are two integers.

#### Len

Optional. **Len** defines the length of the field. If **Len** is decimal (3,1) *ZONED is assigned as the default. If **Len** is character (3), *CHAR is assigned as the default.

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, Types of *BINARY, *CHAR, *PACKED, *ZONED, *DECIMAL, *FLOAT, *INTEGER will require a **Len** . A compiler message will display if the **Len** parameter is needed.

#### TimFmt

Optional. **TimFmt** specifies the format for [time](Time_Formats.html), [date](Date_Formats.html), and [timestamp](Timestamp_Data_Type.html) variables. If the TimFmt parameter is not specified, the format specified by the program is assumed.

#### Rank

Optional. Rank declares an n-dimensional array of indefinite elements. The value given for Rank defines the number of dimensions for the array.

#### Shared

Optional. Indicates that one or more declared programming elements are shared. **Shared** elements are not associated with a specific instance of a class or structure. You can access them by qualifying them either with the class or structure name, or with the variable name of a specific instance of the class or structure. *NO is the default, indicating that the file will not be shared.

- *NO (default) - this file will not be shared.
- *YES - this file will be shared.

#### Access

Optional. The type of access to the file. The default is *Private.

- *PRIVATE (default) - access to the member is accessible only from within their declaration context, including from members of any nested types, for example from within a nested procedure or from an assignment expression in a nested enumeration.
- *PUBLIC - access to the member is accessible from anywhere within the same project, from other projects that reference the project, and from an assembly built from the project.
- *PROTECTED - access to the member is accessible only from within the same class, or from a class derived from this class.
- *INTERNAL - access to the member is accessible from within the same project, but not from outside the project.

#### Modifier

Optional. Modifier controls how properties and methods are overridden in derived classes. *NONE is the default.

- *NONE (default) - specifies that none of the override options are available for properties and methods.
- *MUSTOVERRIDE - specifies that a property or procedure in a base class must be overridden in a derived class before it can be used.
- *NOTOVERRIDABLE - specifies that a property or procedure cannot be overridden in a derived class.
- *OVERRIDABLE - specifies that a property or method can be overridden in a derived class.
- *OVERRIDES - specifies that a property or method overrides a member inherited from a base class.

#### Implements

Optional. Indicates that this class implements the members of an interface. An interface defines a set of properties, events and methods, but does not provide an implementation of them, just a definition. You must implement every member of every interface you specify in this keyword.

#### Attributes

Optional. Allows you to provide one or more attributes that apply to this class. To specify more than one attribute, simply separate them with commas.

#### Like

Optional. Like must be the name of a function already defined in the class. **Type** cannot be a named constant or a literal. In this case, the function will be defined based on the attributes of another function. If **Type** is an array, array element, or a table name, the attributes of an element of the array or table are used to define the field. You can use **Len** parameter to make the declared field longer or shorter than the **Like** parameter entry.

A plus sign (+) preceding the number indicates a length increase; a minus sign (-) indicates a length decrease. You cannot change the number of decimal positions for the function being defined. The function length entry is allowed only for field definitions requiring a length.

#### Event

Optional. The event names that are valid in **EVENT** depend upon the control being used in **Name** . In this case, *CHAR is assumed if there is one integer, and *ZONED is assumed if there are two integers.

#### ReturnAttributes

Optional. Allows you to give attributes to the return value of the BegFunc. This parameter is available to those who desire to add their own attributes. To specify more than one attribute, simply separate them with commas.

### Remarks

A **BEGFUNC** routine must always contain a [LEAVESR](LEAVESR.html) and end with an [ENDFUNC](ENDFUNC.html), as shown in the example below.

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

[Custom Attributes](ecrConCustomAttributes.html)

[DCLSRPARM](DCLSRPARM.html)

[ENDFUNC](ENDFUNC.html)

[LEAVESR](LEAVESR.html)
