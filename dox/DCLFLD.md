---
title: DCLFLD
description: Reference document for Encore DCLFLD, which may be used to declare code block variables, and class and instance field members.

Id: DCLFLD
TocParent: aerLrfOpCodesMain
TocOrder: 470


---

**DCLFLD** declares a working field in the current scope. **DCLFLD** also creates a property if the **Access** parameter is *PUBLIC. DCLFLD also supports the declaration of data areas with the addition of the **DB** and **DataArea** parameters. 

```
DCLFLD 
Name  (Field name)
Type (*BINARY | *BOOLEAN | *BYTE | *CHAR | *DATE | *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8
      | *IND | *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *OBJECT | *ONECHAR | *PACKED 
      | *STRING | *TIME | *TIMESTAMP | *ZONED ) 
Len (Integer Literal, Integer Literal) 
TimFmt (<u>*PGMDFT</u>  | *DMY | *EUR | *HMS | *ISO | *JIS | *JUL | *MDY | *USA | *YMD) 
Shared (<u>*NO</u> | *YES) 
Access (<u>*PRIVATE</u>  |*PUBLIC |*PROTECTED |*INTERNAL) 
Static (<u>*NO</u> | *YES) 
New (<u>*NOOBJECT</u>  | *DFT | Expression List) 
Inz (Constant | Constant Expression)
Attributes (Attribute 1, Attribute 2, ...)
Like (Field name)
DataAreaDB (database name)
DataArea (*Libl/<name> | <string literal> | *YES | *VAR<name> | *LDA)      
```

### Parameters

**Name** 

Required. **Name** is the name of the field to be declared. Name cannot be a named constant or a literal. 

Local variables inside a subroutine can have the same name as global variables or other local variables in other subroutines, and they will not clash. Storage will be reserved locally for each instance of a local variable.


**Type** 

Optional. **Type** can be any of the Special Values denoting a type ( i.e., *CHAR, *BINARY, etc.) or it can be a class name. 

If a **Type** parameter is not given, the **Len** parameter is required. In this case, *CHAR is assumed if there is one integer given and *ZONED is assumed if there are two integers.


**Len** 

Optional. **Len** defines the length of the field. If **Type** is not given, **Len** determines the type of the property: for a one-integer **Len** the type defaults to *CHAR, and a for a two-integer **Len** the type defaults to *ZONED.

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, types of *BINARY, *CHAR, *PACKED, *ZONED, *FLOAT, and *INTEGER will require a **Len**.
Valid values of **Len** for *INTEGER are 2, 4, and 8 and for *FLOAT are 4 and 8. For the fixed-size decimal types *PACKED, *ZONED, and *BINARY, the two-integer length defines the number of digits and the number of decimal positions.

**TimFmt** 

Optional. **TimFmt** specifies the format for [time](Time_Formats.html), [date](Date_Formats.html), and [timestamp](Timestamp_Data_Type.html) variables. If the TimFmt parameter is not specified, the default format specified in the project settings is used.


**Shared** 

Optional. **Shared** indicates whether or not this field is shared, or whether it is associated with a specific instance of a class or structure. The default is *NO. You can access a shared field by qualifying it either with the class or structure name, or with the field name of a specific instance of the class or structure. 

You can use **Shared** only at module, namespace, or file level. This means you can declare shared fields in a source file or inside a module, class, or structure, but not inside a procedure. 

- *NO (default) - specifies that this field is not shared, and is associated with a specific instance of a class or structure.
- *YES - specifies that this field is shared, and is not associated with a specific instance of a class or structure. You can then access a shared variable by qualifying it either with the class or structure name, or with the variable name of a specific instance of the class or structure.


**Access** 

Optional. The type of access to the member. *PRIVATE is the default. 

- *PRIVATE (default) - the member is accessible only from within their declaration context, including from members of any nested types, for example from within a nested procedure or from an assignment expression in a nested enumeration.
- *PUBLIC - the member is accessible from anywhere within the same project, from other projects that reference the project, and from an assembly built from the project.
- *PROTECTED - the member is accessible only from within the same class, or from a class derived from this class.
- *INTERNAL - the member is accessible from within the same project, but not from outside the project.


**Static** 

Optional. **Static** indicates that the declared field will remain in existence and retain its latest values after termination of the procedure in which they are declared. The default is *NO. 

You can use Static only at procedure level. This means you can declare static fields inside a procedure, but not at a class level. 

- *NO (default) - the declared field will not remain in existence and will not retain its latest values after termination of the procedure in which it is declared.
- *YES - the declared field will remain in existence and retain its latest values after termination of the procedure in which it is declared.


**New** 

Optional. Use the **New** parameter when you want to specify a value to a field that is of a **class** type (like System.Text.StringBuilder). You specify either a list of expressions or *DFT to use the parameterless constructor of the class. *NOOBJECT is the default when the **New** parameter is not specified, indicating that this field will contain its default initial value, which for objects is *Nothing. 

- *NOOBJECT (default) - the default when the **New** parameter is not specified, indicating that this field contains the default initial value; which for objects is *Nothing.
- *DFT - constructs an object with a parameterless constructor of the class.
- Expression list - Specify a list of expressions for the default class value. 

Example: DclFld Address type(System.Text.StringBuilder) New(*Dft) <br /> *// Constructs a StringBuilder object with the parameterless constructor. See the help for StringBuilder.* 

Example: DclFld Address type(System.Text.StringBuilder) **New("This is the initial value")** <br /> *// Constructs a StringBuilder object with initial value* "This is the initial value". *See the help for StringBuilder* .


**Inz** 

Optional. **Inz** allows you to specify a default value when a field is of a value type (like *ZONED, *Integer, etc). The value should be a constant (or a constant expression, such as %DECPos ( )), of the appropriate type.


**Attributes** 

Optional. Allows you to provide one or more attributes on the object being defined by the command. To specify more than one attribute, simply separate them with commas. 

Attributes use required, and optional arguments. The required parameters are provided in positional fashion. Positional arguments are arguments that are specified in the order they are declared for the constructor of an attribute. For example, the following code calls the **Developer** constructor of an attribute with two values: BegClass MyClass Attributes(Developer("Joe Cool", 17)) 

You can also use named arguments, which are optional, to directly set the value of properties and fields of the attributes. You specify a named argument by appending ":=" to the name of the argument, followed by the value being specified. Unlike positional arguments, named arguments can be specified in any order. For example, the following code sets the value * **True** for the Reviewed property of the Developer Attribute, and **False** for the Keep field: 
<pre>
 BegClass MyClass Attributes(Developer("Joe Cool", 17, Reviewed:=*True) </pre>

**Note &#8211;** You must use positional arguments for arguments that are used with the attribute’s constructor. Named arguments can only be used to set the values of fields and properties of attribute classes.


**Like** 

Optional. Like must be the name of a field already defined in the class. **Type** cannot be a named constant or a literal. In this case, the field will be defined based on the attributes of another field. If **Type** is an array, array element, or a table name, the attributes of an element of the array or table are used to define the field. You can use **Len** parameter to make the declared field longer or shorter than the **Like** parameter entry. 

A plus sign (+) preceding the number indicates a length increase; a minus sign (-) indicates a length decrease. You cannot change the number of decimal positions for the field being defined. The field length entry is allowed only for field definitions requiring a length.


**DB** 

Optional. Specifies the database in which the data area resides.


**DataArea** 

Optional. Specifies the data area. Valid values are:


- A name - in which case the data area is ***LIBL** /< **name** >.
- A string literal - in which case the data area is **<string
                            literal>**  or ***LIBL/<string literal** 
                        > if the string literal doesn’t contain a library name.
- *YES -  to specify that the data area has the same name as the field.
- *VAR <name> - the name of the data area is whatever the value
                        of variable <name> is at runtime.
- *LDA to specify the local data area.


### Remarks
**Note &#8211;** You should code your declaration statements at the beginning of the code region of the class or routine to which it applies (i.e., BegClass, BegConstructor, BegFunc, BegGet, BegSet, BegSr). If a declaration statement initializes the value of a variable via INZ or New, it will be initialized before any other statement makes reference to it. 

Variables declared with **DCLFLD** are available to all code within the region containing the **DCLFLD** op code. If they are declared in a program, class, or structure, but outside any procedure, they can be accessed from anywhere within that program, class, or structure. To specify their accessibility in more detail, include the **Access** parameter options of *PRIVATE, *PUBLIC, *PROTECTED and *INTERNAL. 
Variables declared inside a procedure or a block are accessible only from
        within that procedure or block. You cannot use any of the accessibility
        keywords for such variables.

**DCLFLD** can declare the data type of a variable and initialize its contents. The declaration statements in the following example declare an **Integer** variable, a **Boolean** variable, and an object variable. These are initialized, respectively, to 20, **True** , and a newly created instance of the **Label** class in the **System.Windows.Forms** namespace. 
<pre class="prettyprint"> DCLFLD Name (Quantity) Type (*Integer) Len (2) Inz (20)
   DCLFLD Name (FirstTry) Type (*Boolean) Inz (*True)<br />   DCLFLD Name (MyLabel) New (System.Windows.Forms.Label() ) </pre>

If you do not specify an initialization value for a variable, Encore RPG initializes it to the default value for its data type. The default initialization values are as follows: 

- 0 for all numeric types (including (* **Byte** ).
- Binary 0 for * **Char.**
- ***Nothing**  for all reference types (including * **Object** , * **String** ,
                and all arrays). Don't forget that attempting to reference these types before
                you have set them to a value will result in a "object not instanced" runtime
                error.
- ***False**  for **Boolean.**
- 12:00 AM of January 1 of the year 1 for * **Date.**

Each element of a structure or array is initialized as if it were a separate variable. 

You can initialize the values of an array by surrounding the initialization values with brackets ([]). The following example creates an array with four elements: 
<pre class="prettyprint"> **DCLFLD**  Name (Array1) Type (*Integer) Inz [0, 1, 2, 3] </pre>

A variable with ***Public** access can be either early bound or late bound. Access to Protected, Internal, and Private variables cannot be late bound. This means you cannot access members on a late-bound object variable unless it is declared as * **Public** . If you attempt to do this, the compiler does not generate an error, but an error occurs at run-time. A static variable has a longer lifetime than that of the procedure in which it is declared. The boundaries of the variable's lifetime depend upon where the procedure is declared and whether or not it is **Shared** . 

- If the procedure is declared in a module, its static variables are initialized
                the first time the procedure is called, and they continue to exist until your
                program terminates execution.
- If the procedure is declared as **Shared** 
                within a class or structure, its static variables are initialized the first
                time the procedure is called either on a specific instance or on the class or
                structure itself. They remain in existence until the program terminates.
- If the procedure is declared within a class or structure and is not **Shared** ,
                its static variables are associated with each individual instance of the class
                or structure. They are initialized the first time the procedure is called in
                that instance, and they continue to exist until that instance is released.

**There are 3 ways to use DCLFLD to create objects in Encore RPG:** 

1. DCLFLD myWord1 Type(Word.Application) // Type is LibraryName.ObjectName

2. DCLFLD myWord2 Type("{000209FF-0000-0000-C000-000000000046}") // Type is ClassId String Literal

3. DCLFLD myWord3 Type("Word.Application.8") //Type is Prog ID

The First way uses the **LibraryName.Objectname** . For this form to work, the Object has to be referenced from the IDE. This means the user has to add an **explicit** reference to this Library by using the References Dialog box. If not, this line would cause a compile error. 

The Second and third way uses the ClassID string and the ProgId string respectively. If one knows the ClassID or the ProgId of the object he wants to use, he can use these forms. The object doesn’t have to be referenced by using the References dialog to use an object this way. 

If Microsoft Word is installed on your machine, then you could add a Reference to it from the References dialog and use Form1. 

If by looking at the Object Browser, or another tool, you know the ClassID or ProgId of Word, then you could use examples 2 or 3. 

In the case of Form2 and Form3, if the ClassId or ProgId was not resolved (i.e., the compiler could not find it in the registry) then the Property names and Method names will be resolved at run-time. Otherwise, they will be resolved at compile-time and error messages will be given for errors in Property names and methods. 

**Example** 

```
// Declare a character field, 10 bytes	long, and move data into it. 

  DCLFLD Name(CHAR10) Type(*CHAR) Len(10)
  CHAR10 = "ABCDEFGHIJ"

// Declare a packed numeric field, 7 long, 2 decimals, and initialize it to 12345.67.

  DCLFLD Name(PACK72) Type(*PACKED) Len(7,2)
  PACK72 = 12345.67

// Declare a zoned numeric field, 7 long, 2 decimals, and initialize it to 76543.21.

  DCLFLD Name(ZONE72) Type(*ZONED) Len(7,2)
  ZONE72 = 76543.21

// Declare a binary data field, 11 long, 2 decimals, and assign a value to it with an expression.

  DCLFLD Name(BIN112) Type(*BINARY) Len(9,2)
  BIN92 = PACK72 + ZONE72
```

### See Also
[Custom Attributes](/concepts/assemblies/CustomAttributes.html)

[DCLKFLD](DCLKFLD.html)

[DCLALIAS](DCLALIAS.html) 
