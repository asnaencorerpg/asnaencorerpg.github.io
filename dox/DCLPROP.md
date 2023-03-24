---
title: DCLPROP

Id: DCLPROP
TocParent: aerLrfOpCodesMain
TocOrder: 123


---

Delcares a property routine.

```

 **DCLPROP** 
 **Name**  (Function name)
Type (*BOOLEAN | *BINARY | *BYTE | *CHAR | *DATE | *IND | *PACKED | *TIME | *TIMESTAMP | *ZONED | 
      *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 | *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *OBJECT | *STRING | name | String Literal | Library.Object) <br />Len (Length Integer, [Decimal Positions Integer])<br />TimFmt (*<u>PGMDFT</u> | *MDY | *DMY | *YMD | *JUL| *ISO | *USA | *EUR| *JIS| *HMS)<br />Rank (IntegerLiteral)<br />Shared (<u>*NO</u> | *YES) <br />Access (<u>*PRIVATE</u> | *INTERNAL | *PUBLIC | *PROTECTED) <br />Modifier (<u>*NONE</u> | *MUSTOVERERIDE | *NOTOVERRIDABLE | *OVERRIDABLE | *OVERRIDES)<br />Implements (Interface name list)  <br />GetAccess (<u>*DFT</u> | *PRIVATE | *INTERNAL | *PUBLIC | *PROTECTED) SetAccess (<u>*DFT</u> | *PRIVATE | *INTERNAL | *PUBLIC | *PROTECTED)

Attributes (Attribute 1, Attribute 2, ...)<br />

Like (Property name)
```


### Parts

**Name** 

Required. The name of the property.


**Type** 

Required. **Type** can be any of the "*" Types (*CHAR, *BINARY, etc.) or it can be the name of a field already defined in the program, a string literal or a library object, as described below. If Type is *BOOLEAN, you can use the *TRUE or *ON and *FALSE or *OFF special values to indicate **True** or **False** . See [Type Parameter](Type_Parameter.html) for further information. 

A string literal, which defines an *OBJECT variable of a particular type. The string literal must represent: 

- A valid program id registered on your system at compile time.
- A valid class id registered on your system at compile time.
- A valid interface name registered on your system at compile time.
- A name of the form Library.Object, where Library is the name of one of the libraries selected in the new up and coming object libraries dialog, and Object is valid object name within that library.

If a **Type** parameter is not given, the <span style="FONT-WEIGHT: bold"> Len </span>parameter is required. In this case, *CHAR is assumed if there is one integer, and *ZONED is assumed if there are two integers.


**Len** 

Optional. **Len** defines the length of the field. If **Len** is decimal (3,1) *ZONED is assigned as the default. If **Len** is character (3), *CHAR is assigned as the default. 

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, types of *BINARY, *CHAR, *PACKED, *ZONED, *DECIMAL | *FLOAT, *INTEGER will require a **Len** . A compiler message will display if the **Len** parameter is needed.


**TimFmt** 

Optional. **TimFmt**  specifies the format for [time](Time_Formats.html),
                [date](Date_Formats.html), and [timestamp](Timestamp_Data_Type.html)
                variables. If the TimFmt parameter is not specified, the format specified by
                the program is assumed.


**Rank** 

Optional. Rank declares an n-dimensional array of indefinite elements. The value given for Rank defines the number of dimensions for the array.


**Shared** 

Optional. Indicates that one or more declared programming elements are shared. **Shared** elements are not associated with a specific instance of a class or structure. You can access them by qualifying them either with the class or structure name, or with the variable name of a specific instance of the class or structure. *NO is the default, indicating that the property will not be shared. 

- *NO (default) - this property will not be shared.
- *YES - this property will be shared.


**Access** 

Optional. The type of access to the property. The default is *PRIVATE, indicating that the property will not be shared. 

- *PRIVATE (default) - access to the member is accessible only from within their declaration context, including from members of any nested types, for example from within a nested procedure or from an assignment expression in a nested enumeration.
- *PUBLIC - access to the member is accessible from anywhere within the same project, from other projects that reference the project, and from an assembly built from the project.
- *PROTECTED - access to the property is accessible only from within the same class, or from a class derived from this class.
- *INTERNAL - access to the member is accessible from within the same project, but not from outside the project.


**Modifier** 

Optional. Modifier controls how properties and methods are overridden in derived classes.*NONE is the default. 

- *NONE (default) - specifies that none of the override options are available for properties and methods.
- *MUSTOVERRIDE - specifies that a property or procedure in a base class must be overridden in a derived class before it can be used.
- *NOTOVERRIDABLE - specifies that a property or procedure cannot be overridden in a derived class.
- *OVERRIDABLE - specifies that a property or method can be overridden in a derived class.
- *OVERRIDES - specifies that a property or method overrides a member inherited from a base class **.** ****


**GetAccess** 

Optional. The type of access to the property's Get method. The default is *dft, indicating that the method will be shared according to the Access keyword. 

Either this keywordor SetAccess can be set, not both. 

The value specified must be more restrictive than the one specified in the property’s Access keyword. If Access is not specified, this should not be specified either, as the default for Access is *private and there is no more restrictive value. 

- *DFT (default) - access to the member's Get method is possible as defined by the Access keyword.
- *PRIVATE (default) - access to the member's Get method is possible only from within their declaration context, including from members of any nested types, for example from within a nested procedure or from an assignment expression in a nested enumeration.
- *PUBLIC - access to the member's Get method is possible from anywhere within the same project, from other projects that reference the project, and from an assembly built from the project.
- *PROTECTED - access to the property's Get method is possible only from within the same class, or from a class derived from this class.
- *INTERNAL - access to the member's Get method is possible from within the same project, but not from outside the project.


S **etAccess** 

Optional. The type of access to the property's Set method. The default is *dft, indicating that the method will be shared according to the Access keyword. 

Either this keyword or GetAccess can be set, not both. 

The value specified must be more restrictive than the one specified in the property’s Access keyword. If Access is not specified, this should not be specified either, as the default for Access is *private and there is no more restrictive value. 

- *DFT (default) - access to the member's Set method is possible as defined by the Access keyword.
- *PRIVATE (default) - access to the member's Set method is possible only from within their declaration context, including from members of any nested types, for example from within a nested procedure or from an assignment expression in a nested enumeration.
- *PUBLIC - access to the member's Set method is possible from anywhere within the same project, from other projects that reference the project, and from an assembly built from the project.
- *PROTECTED - access to the property's Set method is possible only from within the same class, or from a class derived from this class.
- *INTERNAL - access to the member's Set method is possible from within the same project, but not from outside the project.


**Implements** 

Optional. Indicates that this property implements the members of an interface. An interface defines a set of properties, events and methods, but does not provide an implementation of them, just a definition. You must implement every member of every interface you specify in this keyword.


**Attributes** 

Optional. Allows you to provide one or more attributes on the object being defined by the command. To specify more than one attribute, simply separate them with commas. 

Attributes use required, and optional arguments. The required parameters are provided in positional fashion. Positional arguments are arguments that are specified in the order they are declared for the constructor of an attribute. For example, the following code calls the **Developer** constructor of an attribute with two values: 

BegClass MyClass Attributes(Developer("Joe Cool", 17)) 

You can also use named arguments, which are optional, to directly set the value of properties and fields of the attributes. You specify a named argument by appending ":=" to the name of the argument, followed by the value being specified. Unlike positional arguments, named arguments can be specified in any order. For example, the following code sets the value * **True** for the reviewed property of the Developer Attribute, and ***False** for the ```Keep``` field: 

BegClass MyClass Attributes(Developer("Joe Cool", 17, Reviewed:=*True)) 

**Note** You must use positional arguments for arguments that are used with the attribute’s constructor. Named arguments can only be used to set the values of fields and properties of attribute classes.



**Like** 

Optional. Like must be the name of a property already defined in the class. **Type** cannot be a named constant or a literal. In this case, the property will be defined based on the attributes of another property. If **Type** is an array, array element, or a table name, the attributes of an element of the array or table are used to define the field. You can use **Len** parameter to make the declared field longer or shorter than the **Like** parameter entry. 

A plus sign (+) preceding the number indicates a length increase; a minus sign (-) indicates a length decrease. You cannot change the number of decimal positions for the property being defined. The length entry is allowed only for property definitions requiring a length.


### Remarks
Use **DCLPROP** when creating a property for a class. **BEGSET** and **BEGGET** procedures allow you to set and get the value of the property. 

The field that holds the value will be compiler-declared and usable only by the compiler within the property Get and Set methods. It is not available to the programmer. 

```
dclfld_Firstname    *string           INZ("")
dclfld_Lastname    *string           INZ("") 

DCLPROP FullName Type( *string )       Access ( *public )

```

### See Also
[BEGPROP](BEGPROP.html)
[BEGSR](BEGSR.html)
[Custom Attributes](aerConCustomAttributes.html)
[DCLSRPARM](DCLSRPARM.html)
[ENDPROP](ENDPROP.html)
[LEAVESR](LEAVESR.html) 
