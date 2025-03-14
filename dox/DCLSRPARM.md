---
title: DCLSRPARM

Id: DCLSRPARM
TocParent: aerLrfOpCodesMain
TocOrder: 600


---

Defines the parameters that will be received by [BEGSR](BEGSR.html), [BEGPROP](BEGPROP.html), [BEGPROC](BEGPROC.html), [BEGFUNC](BEGFUNC.html) or [BEGCONSTRUCTOR](BEGCONSTRUCTOR.html). Parameters can be passed by **value** or by **reference** . 

```
 DCLSRPARM
Name  (<u>*NONE</u> | Variable name)
Type (*BINARY | *BOOLEAN | *BYTE | *CHAR | *DATE | *DECIMAL | *FLOAT | *FLOAT4
     | *FLOAT8 | *DECIMAL | *FLOAT4 | *FLOAT8 | *IND | *INTEGER | *INTEGER2 
     | *INTEGER4 | *INTEGER8 | *OBJECT |*ONECHAR | *PACKED | *STRING | *TIME | *TIMESTAMP 
     | *ZONED | Form type, Field, Array, Array Element, Table name, String Literal, 
     Library.Object)
Len (Length Integer, [Decimal Integer])
By (<u>*VALUE</u> | *REFERENCE)
TimFmt (<u>*PGMDFT</u> | *DMY | *EUR | *HMS | *ISO | *JIS | *JUL | *MDY | *USA | *YMD)
Rank (IntegerLiteral)
Attributes (Attribute 1, Attribute 2, ...)
Like (Function name)
Options (*OMIT | *NOPASS) 
[Support for Procedure Parameters]
```

### Parameters

**Name** 

Optional when used to declare parameters for a [DCLPROTOTYPE](DCLPROTOTYPE.html), otherwise Required. **Name** can contain either: 

- *NONE (default). If a specified name is not defined, this default prevents a warning if the parameter is not used.
- The name of the variable already defined.
- A string literal, which defines an *OBJECT variable of a particular type. The string literal must represent:*NONE (default). If a specified name is not defined, this default prevents a warning if the parameter is not used. The name of the variable already defined. A string literal, which defines an *OBJECT variable of a particular type. The string literal must represent:

                <ul type="square" style="LIST-STYLE-TYPE: square">
- a valid program id registered on your system at compile time.
- a valid class id registered on your system at compile time.
- A valid interface name registered on your system at compile time.


**Type** 

Optional. **Type** can be any of the "*" Types (*CHAR, *BINARY, etc.) or it can be the name of a field already defined in the program. 

- **Type** cannot be a named constant or a literal. In this case, the field will be defined based on the attributes of another field.
- If **Type** is an array, array element, or a table name, the attributes of an element of the array or table are used to define the field.
- If **Type** is *BOOLEAN, you can use the *TRUE or *ON and *FALSE or *OFF special values to indicate True or False.

- If a **Type** parameter is not given, the **Len** parameter is required. In this case, *CHAR is assumed if there is one integer, and *ZONED is assumed if there are two integers.
- See [Encore RPG Assemblies](/concepts/assemblies/Assemblies.html) for more information.


**Len** 

Optional. **Len** specifies the length of the variable. If **Len** is specified without a Type parameter, *CHAR is assumed if there is one integer, and *ZONED is assumed if there are two integers.


**By** 

Optional. **By** specifies whether the parameter will be passed to the routine by **value** or by **reference** . 

- *Value (default) - passes the parameter data to the subroutine. If the subroutine modifies the data of a *value SRPARM, the original parm data is unaffected.
- *Reference - a referenced parm is one where the pointer memory location of the variable is passed to the subroutine. Any change made to the parameter data will change the data of the parameter variable in the parameter. When passing parameters by reference, you **must** use the [***** ByRef](StarByRef.html) operator.

**TimFmt** 

Optional. **TimFmt** specifies the format for [time](Time_Formats.html), [date](Date_Formats.html), and [timestamp](Timestamp_Data_Type.html) variables. If the TimFmt parameter is not specified, the format specified by the program is assumed.


**Rank** 

Optional. **Rank** declares an n-dimensional array of indefinite elements. The value given for Rank defines the number of dimensions for the array.


**Attributes** 

Optional. **Attributes** allows you to provide one or more attributes on the object being defined by the command. To specify more than one attribute, simply separate them with commas.


Attributes use required, and optional arguments. The required parameters are provided in positional fashion. Positional arguments are arguments that are specified in the order they are declared for the constructor of an attribute. For example, the following code calls the **Developer** constructor of an attribute with two values: 
<pre>
 BegClass MyClass Attributes(Developer("Joe Cool", 17)) </pre>

You can also use named arguments, which are optional, to directly set the value of properties and fields of the attributes. You specify a named argument by appending ":=" to the name of the argument, followed by the value being specified. Unlike positional arguments, named arguments can be specified in any order. For example, the following code sets the value * **True** for the ```Reviewed``` property of the ```Developer``` Attribute, and **False** for the ```Keep``` field: 
<pre>BegClass MyClass Attributes(Developer("Joe Cool", 17, Reviewed:=*True)</pre>


**Note**    You must use positional arguments for arguments
                that are used with the attribute’s constructor. Named arguments can only be
                used to set the values of fields and properties of attribute classes.


**Like** 

Optional. **Like** must be the name of a property already defined in the class. **Type** cannot be a named constant or a literal. In this case, the property will be defined based on the attributes of another property. If **Type** is an array, array element, or a table name, the attributes of an element of the array or table are used to define the field. You can use **Len** parameter to make the declared field longer or shorter than the **Like** parameter entry.


A plus sign (+) preceding the number indicates a length increase; a minus sign (-) indicates a length decrease. You cannot change the number of decimal positions for the property being defined. The length entry is allowed only for property definitions requiring a length.



**Options** [Support for Procedure Parameters] 

Optional. **Options** is available **only** when using [BEGPROC](BEGPROC.html) procedures. It may contain * **OMIT** or * **NOPASS** , as described below. See **BEGPROC** for an **example** in using the **Options** keyword.


- *OMIT - specifies that the parameter *may* either contain a valid value according to its type, or that the special value *OMIT may be passed instead. Use [%OMITTED](OMITTED_Function.html) to know whether this parameter contains a valid value.
- *NOPASS - specfies that the parameter *may* not be passed in the parameter list. Once a parameter declares this option, all the parameters that follow **MUST** also declare it. Use [%PARMS](PARMS_Function.html) to know how many parameters were actually passed at a **CALLB** site.


**Remarks** 

<div>

The **DCLSRPARM** command comes after a **BEGSR** , **BEGFUNC,** **BEGPROP** or **BEGPROC** command, and defines the parameters that will be received by the subroutine when it is called. One or more **DCLSRPARM** commands can come after a **BEGSR** command. A **DCLSRPARM** command that does not come **immediately** after a **BEGSR** , **BEGFUNC,** **BEGPROP, BEGPROC** or another **DCLSRPARM** command will cause a compiler error. 

The data type ( **Type** ) and length ( **Len** ) can be specified. 

Subroutine parameters are declared as local variables to your subroutine. Thus, multiple subroutines can declare the same parameter name, and the names won't clash. 

When parameters are passed on the **EXSR** , they don't necessarily need to be the same type as specified on the **DCLSRPARM** statement. Encore RPG will attempt to coerce the parameter to the type you give. For example, many parameters are four-byte integers, but if you declare the parm as zoned, the value will be converted/possibly truncated accordingly. Likewise, if you specify character, the parm will be copied to the character as if you were doing a [MOVEL](MOVEL.html) with Pad. The programmer is responsible to make sure that values are not truncated when the receiving parameter is too small.

### See Also
[%OMITTED Function](OMITTED_Function.html)

[%PARMS Function](PARMS_Function.html)

[BEGPROC](BEGPROC.html)

[CALL](CALL.html)

[CALLB](CALL.html)

[DCLPLIST](DCLPLIST.html)

[EXSR](EXSR.html)

[***** ByRef Operator](StarByRef.html) 
