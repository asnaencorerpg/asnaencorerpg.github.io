---
title: DCLDS

Id: DCLDS
TocParent: aerLrfOpCodesMain
TocOrder: 420


---

Declares an internal or external data structure.

```
DCLDS
Name (Character Expression)
Dim (IntegerLiteral, IntegerLiteral, ...)
FldScope (<u>*GLOBAL</u>  | *LOCAL | *PGMDFT)
ExtDesc (<u>*NO</u> | (YES)
DbDesc (<u>*NONE</u> | Database Object | Character Expression)
FileDesc (<u>*DSNAME</u> | Character Literal)
Prefix (prefix name, [Length])
Shared (<u>*NO</u> | *YES) 
Access (<u>*PRIVATE</u> |*PUBLIC |*PROTECTED |*INTERNAL)
Attributes (Attribute 1, Attribute 2, ...)
DataAreaDB (database name)
DataArea (*Libl/<name> | <string literal> | *YES | *VAR<name> | *LDA)
Fields (<u>*ALL</u>  | *KEY | *INPUT | *OUTPUT)
Len (Integral expression)
DspFile (Character Expression, Character Expression)
```

### Parts

**Name** 

Required. The **name** of the data structure.


**Dim** 

Optional. **Dim** allows you to create a multiple occurrence data structure. This can be multi-dimensional. Each Integer Literal on the **Dim** parameter specifies a dimension for the array. Individual data structures can be accessed with the [OCCUR](OCCUR.html) command or with the [ ] operator.


**FldScope** 

Optional. **FldScope** defines whether the subfields will be accessible directly in the program (*GLOBAL) or will require you to use the syntax **: DSName.SubfieldName (*LOCAL)** . The *LOCAL option gives you the ability to create subfields without having to worry about name conflicts with other variables, or with fields on externally described files. The program default is *GLOBAL.


**ExtDesc** 

Optional. **ExtDesc** specifies whether the data structure will be externally described. The default is *NO. 

- *NO (default) - The data structure is not externally described.
- *YES - The data structure is externally described. Note that to define the data structure externally, you must also have valid entries for the DbDesc and FileDesc parameters.


**DbDesc** 

Optional. Database description. Specifies the database to use during compile-time to access the File Description. 

- *NONE – (Default).
- Database Object declaration whose DBName specifies where the compiler will acquire the file description. Used in conjunction with **FileDesc** . Database Objects are defined with the [DCLDB](DCLDB.html) command.
- Character expression - the Database Name to get the description from. Used in conjunction with **FileDesc** .


**FileDesc** 

Optional. **FileDesc** specifies the name of the file in which to find the description of the data structure. This parameter is only used in conjunction with the **ExtDesc *YES** parameter to define the data structure as externally described. 

- *DSName is the default.
- If (EXTDESC *YES) is specified, you need to specify the file name in which to
                        find the data structure description.  If a file name is not specified,
                        then the data structure name becomes the same as the file name.


**Prefix** 

Optional. Prefix is used to partially rename the fields in an externally-described file. The characters specified in the **Prefix Name** are a"String" and are prefixed to the names of all fields defined in all records of the file specified. In addition, you can optionally specify a numeric value to indicate the number of characters, if any, in the existing name to be Replaced. If the length (Len) is not specified, then the name string is attached to the **beginning** of the name. 

If the " **Length** " is specified, it must be a numeric constant containing a value between 0 and 9, with no decimal places. For example, the specification PREFIX(YE, 3) would change the field name "YTDTOTAL" to "YETOTAL". 

Specifying a value of zero is the same as not specifying "Length" at all.


**Shared** 

Optional. **Shared** indicates whether or not this data structure is shared, or whether it is associated with a specific instance of a class or structure. The default is *NO. You can access a shared data structure by qualifying it either with the class or structure name, or with the data structure name of a specific instance of the class or structure. 

You can use **Shared** only at module, namespace, or file level. This means you can declare shared data structures in a source file or inside a module, class, or structure, but not inside a procedure. 

- *NO (default) - specifies that this data structure is not shared, and is associated with a specific instance of a class or structure.
- *YES - specifies that this data structure is shared, and is not associated with a specific instance of a class or structure. You can then access a shared variable by qualifying it either with the class or structure name, or with the variable name of a specific instance of the class or structure.


**Access** 

Optional. The type of access to the data structure. *PRIVATE is the default.

- *PRIVATE (default) - access to the data structure is accessible only from within their declaration context, including from members of any nested types, for example from within a nested procedure or from an assignment expression in a nested enumeration.
- *PUBLIC - access to the data structure is accessible from anywhere within the same project, from other projects that reference the project, and from an assembly built from the project.
- *PROTECTED - access to the data structure is accessible only from within the same class, or from a class derived from this class.
- *INTERNAL - access to the data structure is accessible from within the same project, but not from outside the project.


**Attributes** 

Optional. Allows you to provide one or more attributes that apply to this class. To specify more than one attribute, simply separate them with commas.


**DataAreaDB** 

Optional. Defines the database in which the data area resides. DataAreaDB is optional if the DS is externally-described and the DB for the external description is the same DB where the data area lives. In this case the compiler will use **DBDESC** as the DB for the data area.


**DataArea** 

Optional. Specifies the data area. Valid values are:


- A name - in which case the data area is *LIBL/\<name\>.
- A string literal - in which case the data area is \<string literal\>
                        or *LIBL/\<string literal\> if the string literal doesn’t contain a library name.
- *YES -  to specify that the data area has the same name as the field.
- *VAR \<name\> - the name of the data area is whatever the value of
                        member \<name\> is at runtime.
- *LDA to specify the local data area.


**Fields** 

Optional. Specifies which external file fields to use to declare the Data Structure. Valid values are:


- *ALL - to specify that all of the fields will be part of the data structure.
- *KEY - only the key fields will be part of the data structure.
- *INPUT - only the input fields will be part of the data structure.
- *OUTPUT - only the output fields will be part of the data structure.


**Len** 

Optional. If given, **Len** specifies the length of the data structure. If not given, the length in computed out of the lengths of the individual data structure fields.


**DspFile** 

Optional. For externally described data structures based on display files, this keyword specifies the display file path and the record format to use. The first character expression may contain an absolute or relative path to where the file is located. A tilde '~' character at the beginning of the path can be used to indicate the compiler to replace it with the 'Display file folder' value from the project settigns. The second character expression is the record format name.


### Remarks
One or more subfields must be declared using the [DCLDSFLD](DCLDSFLD.html) command after the **DCLDS** command for internally defined data structures. 

To externally define the data structure, **ExtDesc** must be *YES, in addition to valid entries for the **DbDesc** and **FileDesc** parameters. 

### Example

```
// Declare a simple data structure with two subfields of type *CHAR.
DCLDS Name(DS1) 
    DCLDSFLD Name(DSFLD1) Type(*CHAR) Len(5)
    DCLDSFLD Name(DSFLD2) Type(*CHAR) Len(10)

// Declare a 5 occurrence data structure with two subfields of type *CHAR.
DCLDS Name(DS2) DIM(5)
    DCLDSFLD Name(DSFLD3) Type(*CHAR) Len(5)
    DCLDSFLD Name(DSFLD4) Type(*CHAR) Len(10)

// Declare a simple data structure with two subfields of type *CHAR, which are unique to this data structure.
DCLDS Name(DS3) FLDSCOPE(*LOCAL)
    DCLDSFLD Name(DSFLD1) Type(*CHAR) Len(5)
    DCLDSFLD Name(DSFLD2) Type(*CHAR) Len(10)

// Set up DS1 to contain the literal "ABCDEFGHIJKLMNO".
DSFLD1 = "ABCDE"
DSFLD2 = "FGHIJKLMNO"

// Set up occurrence 2 of DS2 to contain the literal "123451234567890".
OCCUR DS(DS2) NEWINDEX(2)
DSFLD3 = "12345"
DSFLD4 = "1234567890"

// Set up occurrence 4 of DS2 to contain the literal "AAAAABBBBBBBBBB".
DS2[4].DSFLD3 = "AAAAA"
DS2[4].DSFLD4 = "BBBBBBBBBB"

// Set up DS3 to contain the literal "IIIIIJJJJJJJJJJ". The FLDSCOPE of this
// data structure is *LOCAL to avoid confusing DSFLD1 from DS1 and DSFLD1 from DS3.
DS3.DSFLD1 = "IIIII"
DS3.DSFLD2 = "JJJJJJJJ"
```


### See Also
[DCLDS](DCLDS.html)

[DclFmtCycleAttr](DCLFMTCYCLEATTR.html)

[DCLOVERLAYGROUP](DCLOVERLAYGROUP.html)

[Time, Date, and Timestamp Variables](Time_Formats.html)

[Data Structure Changes](DataStructureChanges.html) 
