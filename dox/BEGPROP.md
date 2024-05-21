---
title: BEGPROP

Id: BEGPROP
TocParent: aerLrfOpCodesMain
TocOrder: 120


---

Begins the declaration of a property, with getter and/or setter methods.

```
BEGPROP
Name  (Property name)
Type (*BOOLEAN | *BINARY | *BYTE | *CHAR | *DATE | *IND | *PACKED | *TIME | *TIMESTAMP | *ZONED |
      *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 | *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *OBJECT | *STRING | name | Library.Object) 
Len (Length Integer, [Decimal Positions Integer])
TimFmt (\<ins\>*PGMDFT\</ins\> | *MDY | *DMY | *YMD | *JUL| *ISO | *USA | *EUR| *JIS| *HMS)
Rank (IntegerLiteral)
Shared (<ins>*NO</ins> | *YES) 
Access (<ins>*PRIVATE</ins> | *INTERNAL | *PUBLIC | *PROTECTED) 
Modifier (<ins>*NONE</ins> | *MUSTOVERERIDE | *NOTOVERRIDABLE | *OVERRIDABLE | *OVERRIDES)
Implements (Interface name list)  
Attributes (Attribute 1, Attribute 2, ...)
Like (Property or field name)
GetAccess (<ins>*DFT</ins> | *PRIVATE | *INTERNAL | *PUBLIC | *PROTECTED) 
SetAccess (<ins>*DFT</ins> | *PRIVATE | *INTERNAL | *PUBLIC | *PROTECTED)
```


### Parts

**Name** 

Required. The name of the property.


**Type** 

Optional. **Type** can be any of the Special Values denoting a type ( i.e., *CHAR, *BINARY, etc.) or it can be a class name. 

If a **Type** parameter is not given, the **Len** parameter is required. In this case, *CHAR is assumed if there is one integer given and *ZONED is assumed if there are two integers.


**Len** 

Optional. **Len** defines the length of the field. If **Type** is not given, **Len** determines the type of the property: for a one-integer **Len** the type defaults to *CHAR, and a for a two-integer **Len** the type defaults to *ZONED.

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, types of *BINARY, *CHAR, *PACKED, *ZONED, *FLOAT, and *INTEGER will require a **Len**.
Valid values of **Len** for *INTEGER are 2, 4, and 8 and for *FLOAT are 4 and 8. For the fixed-size decimal types *PACKED, *ZONED, and *BINARY, the two-integer length defines the number of digits and the number of decimal positions.

**TimFmt** 

Optional. **TimFmt** specifies the format for [time](Time_Formats.html), [date](Date_Formats.html), and [timestamp](Timestamp_Data_Type.html) variables. If the TimFmt parameter is not specified, the default format specified in the project settings is used.

**Rank** 

Optional. A value given for **Rank** declares the property to be an array, with the value defining the number of dimensions. For example, Rank(2) declares a two-dimensional array. If **Rank** is not specified, the property is a scalar.


**Shared** 

Optional. Specifies whether the property is **Shared** among all instances of the class. Access shared members by qualifying them with the class or structure name. *NO is the default, indicating that the property is not shared. 

- *NO (default) - this property will not be shared.
- *YES - this property will be shared.


**Access** 

Optional. The type of access to the property. The default is *PRIVATE, indicating that the property will not be accessible outside this class. 

- *PRIVATE (default) - the property is accessible only from within this class.
- *PUBLIC - the property is accessible anywhere the class is also accessible.
- *PROTECTED - the property is accessible only from within this class and from classes derived from it.
- *INTERNAL - the property is accessible from other classes within the same project, but not from outside the project.


**Modifier** 

Optional. **Modifier** controls how properties and methods are overridden in derived classes. *NONE is the default. 

- *NONE (default) - specifies that none of the override options are available for properties and methods.
- *MUSTOVERRIDE - specifies a property or procedure (in an abstract base class) that does not have an implementation and must be overridden (*OVERRIDES) in a derived class before it can be used.
- *NOTOVERRIDABLE - specifies that a property or procedure cannot be overridden in a derived class.
- *OVERRIDABLE - specifies that a property or method can be overridden in a derived class.
- *OVERRIDES - specifies that a property or method overrides a member inherited from a base class.


**Implements** 

Optional. For classes that implement interfaces, a property with **Implements** indicates the implementation of a property in the interface.


**Attributes** 

Optional. Allows you to provide one or more attributes on the object being defined by the command. To specify more than one attribute, simply separate them with commas. 

Attributes use required and optional arguments. The required parameters are provided in positional fashion. Positional arguments are arguments that are specified in the order they are declared for the constructor of an attribute. For example, the following code calls the **Developer** constructor of an attribute with two values: 

BegClass MyClass Attributes(Developer("Joe Cool", 17)) 

You can also use named arguments, which are optional, to directly set the value of properties and fields of the attributes. You specify a named argument by appending ":=" to the name of the argument, followed by the value being specified. Unlike positional arguments, named arguments can be specified in any order. For example, the following code sets the value * **True** for the reviewed property of the Developer Attribute: 

BegClass MyClass Attributes(Developer("Joe Cool", 17, Reviewed:=*True)) 

**Note** You must use positional arguments for arguments that are used with the attribute’s constructor. Named arguments can only be used to set the values of fields and properties of attribute classes.


**Like** 

Optional. Like must be the name of a property or field already defined in the class. **Type** cannot be a named constant or a literal. In this case, the property will be defined based on the type of another member in the class. If **Type** is an array, array element, or a table name, the type of an element of the array or table is used to define the property. If the **Like** field type is fixed-size, you can use the **Len** parameter to make the new type longer or shorter than the type in the **Like** entry. A plus sign (+) preceding the number indicates a length increase; a minus sign (-) indicates a length decrease. For decimal nnumbers, you cannot change the number of decimal positions.

**GetAccess** 

Optional. The type of access to the property's Get method. If not given, the Get method will have the property's **Access** value.

**GetAccess** and **SetAccess** are complementary and only one of them can be set in the property declaration.

The value specified must be more restrictive than the one specified in the property’s Access keyword. If Access is not specified, this should not be specified either, as the default for Access is *private and there is no more restrictive value. 

- *DFT (default) - access to the property's Get method is possible as defined by the Access keyword.
- *PRIVATE (default) - access to the property's Get method is possible only from within the current class.
- *PROTECTED - access to the property's Get method is possible only from within the same class, or from a class derived from this class.
- *INTERNAL - access to the property's Get method is possible from within the same project, but not from outside the project.


**SetAccess** 

Optional. The type of access to the property's Set method. If not given, the Set method will have the property's **Access** value.

**GetAccess** and **SetAccess** are complementary and only one of them can be set in the property declaration.

The value specified must be more restrictive than the one specified in the property’s Access keyword. If Access is not specified, this should not be specified either, as the default for Access is *private and there is no more restrictive value. 

- *DFT (default) - access to the property's Set method is possible as defined by the Access keyword.
- *PRIVATE (default) - access to the property's Set method is possible only from within the current class.
- *PROTECTED - access to the property's Set method is possible only from within the same class, or from a class derived from this class.
- *INTERNAL - access to the property's Set method is possible from within the same project, but not from outside the project.



### Remarks

Use **BEGPROP**  when creating a property for a class. **BEGSET** and **BEGGET**  procedures allow you to set and get the value of the property.

A **BEGPROP** routine ** * must always * ** end with an [ENDPROP](ENDPROP.html) and the [BEGGET](BEGGET.html) routine must also contain a [LEAVESR](LEAVESR.html), as shown below.

```
    dclfld _FirstName *string INZ("") 
    dclfld _LastName *string INZ("") 

    BegProp FirstName *string Access( *public ) 
        BegSet 
            _FirstName = *Propval 
        EndSet 
        BegGet 
            LeaveSR _FirstName 
        EndGet 
    EndProp 

    BegProp Lastname *string Access( *public ) 
        BegSet NewValname( Lname ) 
            _LastName = Lname 
        EndSet 
        BegGet 
            LeaveSR _LastName 
        EndGet 
    EndProp // Read only property 

    BegProp FullName Type( *string ) Access ( *public ) 
        BegGet 
            LeaveSR Value( FirstName + " " + LastName ) 
        EndGet 
    EndProp
```

### See Also
[DCLPROP](DCLPROP.html)

[BEGSR](BEGSR.html)

[Custom Attributes](ecrConCustomAttributes.html)

[DCLSRPARM](DCLSRPARM.html)

[ENDPROP](ENDPROP.html)

[LEAVESR](LEAVESR.html) 
