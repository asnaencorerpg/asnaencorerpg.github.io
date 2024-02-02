---
title: DCLDSFLD

Id: DCLDSFLD
TocParent: aerLrfOpCodesMain
TocOrder: 430


---

Declares a subfield for a data structure.

```
DCLDSFLD 
Name  (name)
Type (*BINARY | *BOOLEAN | *BYTE | *CHAR | *DATE | *DECIMAL | *FLOAT | *FLOAT4 |
      *FLOAT8 | *IND | *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *ONECHAR |
      *PACKED | *TIME | *TIMESTAMP | *ZONED)
Len (Integer Literal, Interger Literal)
Dim (Integer Literal, Integer Literal, ...)
TimFmt (<u>*PGMDFT</u> | *DMY | *EUR | *HMS | *ISO | *JIS | *JUL | *MDY | *USA | *YMD)
Like (Field name)
Overlay (parentField, startPos | *Next)
OverlayArray (parentField, startPos | *Next) 
DataAreaDB (database name)
DataArea (*Libl/<name> | <string literal> | *YES | *VAR<name> | *LDA)
StartAt (Position)
```

### Parts

**Name** 

Required. The name of the data structure subfield.


**Type** 

Optional. **Type** can be any of Special Value ( i.e., *CHAR, *BINARY, etc.) or it can be a class name. If **Type** is *BOOLEAN or *IND, you can use *ON, *TRUE, *ON and *FALSE figurative constants to indicate true and false and "1" and "0", respectively. 

If a **Type** parameter is not given, the **Len** parameter is required. In this case, *CHAR is assumed if there is one integer given and *ZONED is assumed if there are two integers.


**Len** 

Optional. **Len** specifies the length of the field. If **Len** is decimal e.g. Len (3,1) *ZONED is assigned as the default. If **Len** is character e.g. Len (3), *CHAR is assigned as the default. 

If **Type** is packed, then the length is not the number of bytes the packed field fits into, but rather the logical digit length of the field. For example, if you want a 7 digit packed with 2 decimals, code Len (7,2).


**Dim** 

Optional. When **Dim** is specified, the **DCLDSFLD** is treated as an array with all the properties associated with a [DCLARRAY](DCLARRAY.html) statement.


**TimFmt** 

Optional. **TimFmt** specifies the format for [time](Time_Formats.html), [date](Date_Formats.html), and [timestamp](Timestamp_Data_Type.html) variables. If the TimFmt parameter is not specified, the format specified by the program is assumed.


**Like** 

Optional. **Like** must be the name of a field already defined in the class. **Type** cannot be a named constant or a literal. In this case, the field will be defined based on the attributes of another field. If **Type** is an array, array element, or a table name, the attributes of an element of the array or table are used to define the field. You can use **Len** parameter to make the declared field longer or shorter than the **Like** parameter entry. 

A plus sign (+) preceding the number indicates a length increase; a minus sign (-) indicates a length decrease. You cannot change the number of decimal positions for the field being defined. The field length entry is allowed only for field definitions requiring a length.


**Overlay** 

Optional. **Overlay** is supported for *zoned, *char, *packed, and *onechar/*indicator fields, where the overlaid field is any of these types or an array. For *packed, the overlaid field must be either *char or *packed of the same size. The **OVERLAY** keyword overlays the storage of one subfield with that of another subfield.


This subfield will overlay the storage specified by the *overlaid name* parameter at the position specified by the *startpos* parameter. If *startpos* is not specified, it defaults to 1.


- parentField - The name of a subfield defined previously in the current data
                        structure.  See further information below.
- startPos - Optional.  Can be an integer, or *NEXT.  Specifying
                        Overlay (Name:*Next), positions the subfield at the next available position
                        within the overlaid field. This will be the first byte past all other
                        subfields prior to this subfield that overlays the same subfield.  Note:
                        The *startpos*  parameter is in units of bytes, regardless of the
                        types of the subfields.   See further information below.


**The following rules apply to keyword OVERLAY:** 

1. The *overlaid name*  parameter must be the name of a subfield defined previously in the current data
                        structure.
2. The *startpos*  parameter (if specified) must be a value greater than 0
                        with no decimal positions.  It can be a numeric literal, a built-in function returning a numeric value,
                        or a numeric constant. If *startpos*  is a named constant, it must be defined prior to this specification.
3. If the *overlaid name*  parameter is a subfield, the subfield being defined must be contained completely
                        within the subfield specified by the *overlaid name*  parameter.
4. Alignment of subfields defined using the **OVERLAY**  keyword must be done manually. 
                        If they are not correctly aligned, a warning message is issued.
5. If a subfield with overlaying subfields is not otherwise defined, the subfield is implicitly defined as follows: 

                            <li>
                                The start position is the first available position in the data structure.
6. The length is the minimum length that can contain all overlaying subfields. If
                                the subfield is defined as an array, the length will be increased to ensure
                                proper alignment of all overlaying subfields.

</li>

- If the subfield specified by *overlaid name* is an **array** , the **OVERLAY** keyword applies to each element of the array. See restrictions below. 

That is, the field being defined is defined as an array with the same number of elements. The first element of this array overlays the first element of the overlaid array, the second element of this array overlays the second element of the overlaid array, and so on. No array keywords may be specified for the subfield with the **OVERLAY** keyword in this situation. 

If the subfield specified by *overlaid name* is an array and its element length is longer than the length of the subfield being defined, the array elements of the subfield being defined are not stored contiguously. <br /><br /> **Restrictions when the overlaid name is an array:**

Under such a declaration, the subfield becomes a non-contiguous array and has the following usage limitations. 

- Not valid on Result Field of **PARM** .
- Not valid on Factor2 or Result Field of **MOVEA** .
- When used with a **SORTA** , the "parent" array is sorted
                        according to the data values of the non-contiguous array elements.
- Allowed on an **XFOOT** .
- When on the left side of an assignment and used with no index, it follows the
                        rules of having an array on the left (i.e. runs a loop to assign to every
                        element of the array.


**OverlayArray** 

Optional. The **OverlayArray** keyword is used to define a field to overlay an **array** subfield. The elements of the array subfield will be concatenated into one large **scalar** field, before overlaying occurs (RPG/400 behavior). This field can be of any scalar type if it exactly matches the starting position and type of a single array element. Otherwise the field and the array must be either *ZONED or *CHAR.


In contrast to the **Overlay** keyword, which is an element-by-element overlay (RPG/ILE behavior) when overlaying an array, when using **OverlayArray** , the field will be defined as a **Scalar** . 

- ParentField - The name of a subfield defined previously in the current data
                        structure. It must be an array.
- startPos - Optional. Can be an integer, or *NEXT. Specifying
                        OverlayArray (Name:*Next), positions the subfield at the next available position
                        within the overlaid array. This will be the first byte past all other
                        subfields prior to this subfield that overlays the same subfield.  Note:
                        The *startpos*  parameter is in units of bytes, regardless of the
                        types of the subfields.<br />


**DataAreaDB** 

Optional. Specifies the database in which the data area resides.


**DataArea** 

Optional. Specifies the data area. Valid values are:


- A name - in which case the data area is *LIBL/<name>.
- A string literal - in which case the data area is <string literal>
                        or *LIBL/<string literal> if the string literal doesn’t contain a library name.
- *YES -  to specify that the data area has the same name as the field.
- *VAR <name> - the name of the data area is whatever the value of
                        member <name> is at runtime.
- *LDA to specify the local data area.


**StartAt** 

Optional. Specifies the 1-based starting position of this field in the Data Structure buffer. If not given the field starts after the previously declared field in the Data Structure.


### Example

```
DCLDS Name(DS1)
    DCLDSFLD Name(DSFLD1)    Type(*CHAR) Len(5)
    DCLDSFLD Name(DSFLD2)    Type(*ZONED) Len(10,0)
    DCLDSFLD Name(OVERDSFLD) Type(*CHAR) Len(10) Overlay(DSFLD2)
```
        
```
// Declare a simple data structure with two subfields with one overlay of the 1st five characters of DSFLD2
DCLDS Name(DS1)
    DCLDSFLD Name(DSFLD1)    Type(*CHAR) Len(5)
    DCLDSFLD Name(DSFLD2)    Type(*CHAR) Len(10)
    DCLDSFLD Name(OVERDSFLD) Type(*CHAR) Len(5) Overlay(DSFLD2,1)
```

### See Also
[DCLDS](DCLDS.html)


