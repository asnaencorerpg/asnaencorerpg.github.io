---
title: DCLARRAY

Id: DCLARRAY
TocParent: aerLrfOpCodesMain
TocOrder: 370


---

Declares an n-dimensional array.

```
DCLARRAY 
Name  (name)
Dim (Integer Literal, Integer Literal, ...)
Type (*BINARY | *BOOLEAN | *BYTE | *CHAR | *DATE | *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 |
      | *IND | *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *ONECHAR | *OBJECT |
      *PACKED | *STRING | *TIME | *TIMESTAMP | *ZONED)
Len (Length Integer, [Decimal Positions Integer])
TimFmt (<u>*PGMDFT</u> | *DMY | *EUR | *HMS | *ISO | *JIS | *JUL | *MDY | *USA | *YMD)
Rank (IntegerLiteral)
Shared (<u>*NO</u> | *YES)
Access (<u>*PRIVATE</u> | *INTERNAL| *PUBLIC | *PROTECTED) 
Static (<u>*NO</u>  |*YES)
Table (<u>*NAMESPEC</u> | *YES | *NO)
Seq (<u>*NONE</u> | *ASCEND | *DESCEND)
New (<u>*NOOBJECT</u> | *DFT | Character Expression List)
Inz (Constant | Constant Expression)
Attributes (Attribute 1, Attribute 2, ...)
Like (Field name)
```

### Parts

**Name** 

Required. The Name parameter can contain either:

- The name of the variable already defined.
- A string literal, which defines an *OBJECT variable of a particular type. The string literal must represent: 
<ul>
                            <li type="square">

a valid program id registered on your system at compile time.
- a valid class id registered on your system at compile time.
- a valid interface name registered on your system at compile time.

</li>
                    <li>

A name of the form Library.Object, where Library is the name of one of the libraries selected in the new up and coming object libraries dialog, and Object is valid object name within that library. 
</li>
                </ul>


**Dim** 

Optional. The size of the array. Each value in the **Dim** parameter specifies the size of a dimension for the array.


**Type** 

Optional. **Type** can be any of Special Value ( i.e., *CHAR, *BINARY, etc.) or it can be a class name. If Type is *BOOLEAN, you can use the *TRUE or *ON and *FALSE or *OFF special values to indicate **True** or **False** . 

If a **Type** parameter is not given, the **Len** parameter is required. In this case, *CHAR is assumed if there is one integer given and *ZONED is assumed if there are two integers. 

See [Type Parameter](Type_Parameter.html) for more information.


**Len** 

Optional. **Len** defines the length of the field. If **Len** is decimal, e.g. Len (3,1), *ZONED is assigned as the default. If **Len** is character, et. **Len** (3), *CHAR is assigned as the default.


**TimFmt** 

Optional. **TimFmt**  specifies the format for [time](Time_Formats.html),
                [date](Date_Formats.html), and [timestamp](Timestamp_Data_Type.html)
                variables. If the TimFmt parameter is not specified, the format specified by
                the program is assumed.


**Rank** 

Optional. A value given for **Rank** declares the property to be an array, with the value defining the number of dimensions. For example, Rank(2) declares a two-dimensional array. If **Rank** is not specified, the property is a scalar.


**Shared** 

Optional. **Shared** specifies whether or not this array is to be shared. *NO is the default. 

- *NO (default) - this array will not be shared.
- *YES - this array will be shared.


**Access** 

Optional. The type of access to the member. *PRIVATE is the default.

- *PRIVATE (default) - the member is accessible only from within their declaration context, including from members of any nested types, for example from within a nested procedure or from an assignment expression in a nested enumeration.
- *PUBLIC - the array is accessible from anywhere within the same project, from other projects that reference the project, and from an assembly built from the project.
- *PROTECTED - the array is accessible only from within the same class, or from a class derived from this class.
- *INTERNAL - the array is accessible from within the same project, but not from outside the project.


**Static** 

Optional. **Static** indicates that the declared array will remain in existence and retain its latest values after termination of the procedure in which they are declared. The default is *NO. 

You can use Static only at procedure level. This means you can declare static arrays inside a procedure, but not at a class level. 

- *NO (default) - the declared array will not remain in existence and will not retain its latest values after termination of the procedure in which it is declared.
- *YES - the declared array will remain in existence and retain its latest values after termination of the procedure in which it is declared.


**Table** 

Optional. The number of dimensions of a multidimensional array parameter determines whether an array should behave like an RPG table. Tables have an implicit index, which can be manipulated with the [LOOKUP](LOOKUP.html) op code and the [%TLOOKUP](TLOOKUP_Function.html) function. The default is *NAMESPEC. 

- *NAMESPEC - (default) specifies that arrays that have a name beginning with " **TAB** " are considered tables.
- *YES - specifies the array **is** a table regardless of the name.
- *NO - specifies that it is **not** a table, regardless of the name.


**Seq** 

Optional. The **Seq** parameter determines the presumed sequence of the array. The programmer must ensure that entries are actually in the correct sequence. This aids the **LOOKUP** command to be able to search the array faster, because not every entry in the array has to necessarily be searched. *ASCEND or *DESCEND must be specified to use [%LOOKUPLT, %LOOKUPLE, %LOOKUPGT, or %LOOKUPGE.](LOOKUP_Function.html)


**New** 

Optional. **New** allows you to specify a value when a field is of a class type (like System.Text.StringBuilder). You specify either a list of expressions or *DFT to use the parameterless constructor of the class. *NOOBJECT is the default. 

- *NOOBJECT (default) - allows you to use the parameterless constructor of the class.
- *DFT - allows you to use the parameterless constructor of the class.
                        <br />
 Example: DclFld Address type(System.Text.StringBuilder) **New(*Dft)** <br /> *// Constructs a StringBuilder object with the parameterless constructor. See
                            the help for StringBuilder.*
- Character Expression List - specify a list of expressions for the default class value.
                        <br /> Example: DclFld Address type(System.Text.StringBuilder) **New("This is the initial value")** 
 <br /> *// Constructs a StringBuilder object with initial value* 
                        "This is the initial value". *See the help for StringBuilder.*


**Inz** 

Optional. **Inz** allows you to specify a default value when a field is of a value type (like *Zoned, *Integer, etc). The value should be a constant (or a constant expression, such as %DecPos ( )), of the appropriate type.


**Attributes** 

Optional. Allows you to provide one or more attributes that apply to this class. To specify more than one attribute, simply separate them with commas.


**Like** 

Optional. Like must be the name of a field already defined in the class. **Type** cannot be a named constant or a literal. In this case, the field will be defined based on the attributes of another field. If **Type** is an array, array element, or table name, the attributes of an element of the array or table are used to define the field. You can use **Len** parameter to make the declared field longer or shorter than the **Like** parameter entry. 

A plus sign (+) preceding the number indicates a length increase; a minus sign (-) indicates a length decrease. You cannot change the number of decimal positions for the field being defined. The field length entry is allowed only for field definitions requiring a length.


### Remarks
**DCLARRAY** declares an array. Either **Dim** or **Rank** must be specified for the array. **Dim** gives the array a fixed size, specifying the number of elements in each of its its dimensions. **Rank** specifies the number of diensions, and the array must be initialized before it can be used. Array elements are accessed by using the **[ ]** operators. 

Use [DCLDSFLD](DCLDSFLD.html) to declare an array within a data structure. 

**For DIM arrays**
Depending on the type of the array elements, one of the two keywords will contain information for initialization: 

**If the element is scalar** (i.e. a numeric type, a char type, a string, etc) then INZ contains the initial value. 

```
// this initializes each element of myIntArray to the value 9
DclArray myIntArray DIM(8) type(*integer) len(4) INZ(9)
``` 

**If the element type is a class** (e.g. System.Text.StringBuilder), then the NEW keyword contains the arguments to the constructor. Each element contains its own instance, even though they are all obtained with the same constructor arguments. 
<pre class="prettyprint">
// this initializes each element of mySBArray // to *new System.Text.StringBuilder("Hello World")
DclArray mySBArray DIM(10) type(System.Text.StringBuilder) NEW("Hello World")'</pre>

**For RANK arrays**
The **INZ** keyword is not allowed, it is an error to use **RANK** and **INZ** in the same **DclArray** . The **NEW** keyword, if given, must contain a comma separated list of indices to give to the array constructor. The list of indices must match the RANK of the array. The array will be initialized to the size specified, and its elements will be initialized to the default value of the element type. 

```
// this creates myIntArray with 45 (two-dimensional 9 X 5) elements initialized to 0 (the default value for integers) 
DclArray myIntArray RANK(2) type(*integer) len(4) NEW(9,5) 
// this creates myCharArray with 10 elements initialized to "        " (8 blanks, the default value for *char 8) 
DclArray myCharArray RANK(1) type(*char) len(8) NEW(10) 
// this creates mySBArray with 5 elements initialized to *nothing (the default value for class objects) 
DclArray mySBArray RANK(2) type(System.Text.StringBuilder) NEW(5)
```

You can initialize the number of elements and their content when the array is instanced using the following syntax: 
```
Dclarray MyStrArr type(*string) rank(1)
// below will create array of 5 elements
MyStrArr = *new *string[] {"The", "quick", "brown", "fox", "jumped"} 
Dclarray MyIntArr type(*integer4) rank(1) 
// below will create array of 3 elements 
MyIntArr = *new *integer4[] {10, 100, 1000} 
```

### Example
```
  DCLFLD Name($X) Type(*ZONED) Len(2,0) 
  DCLFLD Name($Y) Type(*ZONED) Len(2,0)<br /> //Declare an 8 x 8 two-dimensional array of characters within a data structure called MyDs. DclDs Name(MyDs)
  DclDsFld Name(Z8by8) DCLFLD(8,8) Type(*char) Len(5) 

 // Initialize the array to all *'s. X = *zeros 
     Do 1 8 $X 
        $Y = *zeros 
        Do 1 8 $Y
            Z8by8[$X,$Y] = "*****" 
        Enddo
     Enddo 

 // Declare an 8 x 8 two-dimensional array of characters. DCLARRAY Name(ARR1) DIM(8,8) Type(*CHAR) Len(10) 

 // Initialize the array to all *'s. $X=0 
  DOUNTIL ($X=8) 
    $Y=0 
    $X=$X+1 
    DOUNTIL ($Y=8)
      $Y=$Y+1
      ARR1[$X,$Y] = "**********"
    ENDDO
  ENDDO
```

### See Also
[Arrays Overview](ecrConArraysOverview.html)

[Custom Attributes](ecrConCustomAttributes.html)

[DCLDS](DCLDS.html)

[DCLDSFLD](DCLDSFLD.html)

[DCLOVERLAYGROUP](DCLOVERLAYGROUP.html)

[DCLFLD](DCLFLD.html)

[LOOKUP](LOOKUP.html)

[%LOOKUP](LOOKUP_Function.html)

[%TLOOKUP](TLOOKUP_Function.html) 
