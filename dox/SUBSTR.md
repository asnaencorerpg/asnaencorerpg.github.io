---
title: SUBSTR

Id: SUBSTR
TocParent: aerLrfOpCodesMain
TocOrder: 1500


---

Returns a substring from **BaseStr** , starting at the location specified in **BaseStr** for the length specified in **SubLen** , and places it in the **Target** . 

```
SUBSTR
BaseStr (Character Operand)
StartPos (Numeric Expression | 1)
SubLen (Numeric Expression | <u>*ALL</u>) Target  (Character Operand)
Fill (<u>*NOPAD</u> | *PAD)
Err (Indicator Variable | *EXTENDED)
Type (<u>*NONE</u> | *BINARY | *BOOLEAN | *BYTE | *CHAR | *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 |
    *IND | *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *ONECHAR | *PACKED | *ZONED)
Len (Length Integer, [Decimal Integer])
```

### Parameters

**BaseStr** 

Required. Must contain either the base character string or the base character string followed by ":"; followed by the start location.


**StartPos** 

Optional. Must be numeric type with no decimal positions and can be a named constant, array element, field name, literal, or table name. If no start location is specified, a value of 1 is used.


**SubLen** 

Optional. Can contain the length value of the string to be extracted from the base string specified in **BaseStr** . **SubLen** must be numeric with no decimal positions and can contain either a field name, array element, table name, literal, or named constant.


**Target** 

Required. The length of the **Target** should be at least as large as the length designated in **SubLen** . Should the substring be longer than the field specified in the **Target** , the substring will be truncated from the right. 

The start location and the length of the substring to be extracted must be positive integers.


**Fill** 

Optional. Specifies if you want to fill, or pad the **Target** with blanks. The default is *NOPAD. 

- *NOPAD indicates that the **Target** will not be padded with blanks.

- *PAD indicates that the **Target** will be padded with blanks.


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - The specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


**Type** 

Optional. Can be any of the **Types** listed. *NONE is the default. See [Type Parameter](Type_Parameter.html) for further information.


**Len** 

Optional. Defines the length of the field. If **Len** is decimal (3,1) *ZONED is assigned as the default. If **Len** is character (3), *CHAR is assigned as the default. 

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, Types of *CHAR, *PACKED, *ZONED will require a **Len** . A compiler message will display if the **Len** parameter is needed.


### Remarks
To be considered numeric, each character in the field, except the low-order character, must contain a hexadecimal 3 zone and a digit from 0 through 9. The number has a negative value when the low-order character contains a hexadecimal 7 zone, and a digit from 0 through 9 (alphabetic characters "p" through "y"). 

### Example

```

/* The **SubStr**  operation extracts the substring from **BaseStr**  starting at 
position 3 for a length of 2. The value "NA" is placed in **Target**  MyTarget. Indicator 90 is not set on because 
no error occurred. */

Beginhere = 3
MyString = "ASNARP"
SubStr BaseStr(MyString) StartPos(Beginhere) Sublen(2) Target(MyTarget) Err (*IN90)

/* In this **SubStr**  operation, the length is greater than the length of the string minus the start 
position plus 1. As a result, indicator 90 is set on and the **Target** is not changed. */

BeginHere = 4
MyString = "ASNARP"
SubStr MyString BeginHere 4 MyTarget Err (*IN90)

/* In this **SubStr**  operation, 3 characters are substringed starting at the fifth position of the 
base string. Because Fill(*Pad) is not specified, only the first 3 characters of MyTarget are changed. 
When the operation is completed, MyTarget contains "123XXXXX". */

Length = 3
Beginhere = 5
MyString = "ASNA123"
MyTarget = "XXXXXXXX"
SubStr MyString Beginhere Length MyTarget Err (*IN90)

/* This example is the same as the previous one except that "Fill(*Pad) is specified, and the result is padded 
	with blanks. When the operation is completed, MyTarget equals "123bbbbb". */

Length = 3
Beginhere = 5
MyString = "ASNA123"
MyTarget = "XXXXXXXX"
SubStr MyString Beginhere Length MyTarget Err (*IN90) Fill(*Pad)

/* In the following example, CityState contains the string "San Antonio, Texas". The Scan operation is used to locate 
   the separating comma (position 12 in this illustration). **SubStr**  without length to extract places the string 
   starting at position 14 and continuing for the length of the string in field State. When the operation is completed,
   State contains "Texas". */

DclFld CommaPlace *PACKED Len(2,0)
Scan CmpStr(",") BaseStr(CityState) 
FndPos(CommaPlace)
CommaPlace = CommaPlace + 1
SubStr BaseStr(CityState) StartPos(CommaPlace) Target(State) Fill(*Pad)

/* Before the operations MyString = "bbbAsnabbbbbb". MyResult is a 10 character field which contains "ABCDEFGHIJ". 
   The Check operation locates the first nonblank character and sets on indicator 10 if such a character exists. If 
   *IN10 is on, the **SubStr**  operation substrings MyString starting from the first non-blank to the end of 
   MyString. Padding is used to ensure that nothing is left from the previous contents of the **Target** . 
   After the operations MyResult = "Asnabbbbbb". */

DclFld FirstBlank *PACKED Len(2,0)
Check CmpStr(" ") BaseStr(MyString) Startpos(FirstBlank) Fnd(*In10)
If *In10
  SubStr MyString FirstBlank Target(MyResult) Fill(*Pad) Err (*In90)
Endif 
```

