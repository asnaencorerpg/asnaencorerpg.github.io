---
title: SCAN

Id: SCAN
TocParent: aerLrfOpCodesMain
TocOrder: 1410


---

Scans a base string for an occurrence of the compare string. A starting position within the base string can be specified as well as the length of base string to be compared. 

```
SCAN
CmpStr  (Character Expression)
CmpLen (<u>*ALL</u> | Numeric Expression)
 BaseStr  (Character Expression)
StartPos (Numeric Expression | <u>1</u>)
FndPos (<u>*NONE</u> | Numeric Expression)
Err (Indicator Variable | *EXTENDED)
Fnd (Indicator Variable)
```

### Parts

**CmpStr** 

Required. Must contain the string to be compared to **BaseStr** and be character type. It can be a field name, array element, named constant, data structure name, literal, or table name. Leading, trailing, or embedded blanks specified in the compare string are included in the **SCAN** operation.


**CmpLen** 

Optional. Must be numeric with no decimal positions. It can be a field name, named constant, array element, literal, or table name. The default value is the length of **CmpStr** .


**BaseStr** 

Required. Must contain the base string to be compared to. It must be character type. It can be a field name, array element, named constant, data structure name, literal, or table name.


**StartPos** 

Optional. Must be numeric type with no decimal positions and can be a named constant, array element, field name, literal, or table name. The value can not be greater than the length of **BaseStr** . If no start location is specified, a value of 1 is used.


**FndPos** 

Optional. This parameter must be specified if **Fnd** is not. If specific, it must be a numeric field with zero decimal positions and can contain a field name, array element, array name, or table name and will contain the numeric value of the first occurrence (from left) of **CmpStr** in **BaseStr** , if found. 

**FndPos** is set to 0 if the string is not found. If this contains an array, each occurrence of the compare string is placed in the array with the leftmost occurrence in element 1. The array elements following the element containing the rightmost occurrence are all zero. The resulting array should be as large as the field length of the base string. 

Note the following: 

- The strings are indexed from position 1.
- If the start position is greater than 1, the result contains the position relative to the beginning of **BaseStr** , not relative to the start position.
- Figurative constants cannot be used in the **CmpStr** , **BaseStr** , or **FndPos** .
- No overlapping within data structures is allowed for **CmpStr** and the result or **StartPos** and the result.


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - The specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


**Fnd** 

Optional. **Fnd** (or FD indicator) will be set if the string being scanned for is found. This parameter must be specified if **FndPos** is not. Note that you can also use the [%FOUND](FOUND_Function.html) function.


### Remarks
**SCAN** begins at the leftmost character of **BaseStr** at **StartPos** and continues character by character, from left to right, comparing the characters in **BaseStr** to those in **CmpStr** for the **CmpLen** specified. If the result is not an array, the **SCAN** operation will locate only the first occurrence of the compare string. To continue scanning beyond the first occurrence, use the result from the previous **SCAN** operation to calculate the starting position of the next **SCAN** . If the result is a numeric array, as many occurrences as there are elements in the array are noted. 

If no occurrences are found, **FndPos** is set to zero. If **FndPos** is an array, all its elements are set to zero. 

The **SCAN** operation is case-sensitive. A compare string specified in lowercase will not be found in a base string specified in uppercase. 

### Example

```
/* The SCAN operation finds the substring "RPG" starting in position 5 in BaseStr; 5 is placed in the FndPos(Result).
   Indicator 90 is set on because the string is found. Because no starting position is specified, the default of 1 
   is used. */

Scan CmpStr("RPG") BaseStr("ASNARPG") FndPos(Result) Fnd(*In90)

/* This SCAN operation scans the string in Field1(F2) for an occurrence of the string in Field2 (F1) starting at 
   position 3. The "Y" in position 1 of the base string is ignored because the scan operation starts from position 3. 
   The operation places the values 5 and 6 in the first and second elements of the MyArray array. Indicator 90 is set on. */ 

DclArray Name(MyArray) Dim(10) Type(*zoned) Len(1,0) 
Field1 = "YARRYY"
Field2 = "Y" 
Scan Field2 BaseStr(Field1) StartPos(3) FndPos(MyArray) Fnd(*In90) 

/* This SCAN operation scans the string in Field1 (F2), starting at position 2, for an occurrence of the string in 
Field2(F1) for a length of 3. Because "RPG" is not found in FIELD1, INT90 is set to zero and indicator 90 is set off. */ 

Field1 = "Visual" 
Index = 2
Field2 = "RPG"
Scan Field2 3 Field1 Index Int90 Fnd(*In90)  
```

#### See Also
[Character Expression](Character_Expression.html)

[Numeric Expression](Num_Expression.html) 
