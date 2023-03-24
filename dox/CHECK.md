---
title: CHECK

Id: CHECK
TocParent: aerLrfOpCodesMain
TocOrder: 270


---

Verifies that each character in a base string or array is among the characters in the comparator string. 

```

 **CHECK
CmpStr**  (Character Expression)
 **BaseStr**  (Character Expression)
NoMatch (Numeric Variable | <u>*NONE</u>)
StartPos (Numeric Expression | <u>1</u>)
Err (Indicator Variable | *EXTENDED) 
Fnd (Indicator Variable)
Type (<u>*NONE</u> | *BINARY | *BOOLEAN | *BYTE | *CHAR | *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 | *IND |
      *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *ONECHAR | *PACKED | *ZONED)
Len (Length Integer, [Decimal Integer])
```

### Parts

**CmpStr** 

Required. Contains a character expression that is used to compare against the **BaseStr** .


**BaseStr** 

Required. Contains a character expression that contains the string to compare with **CmpStr** .


**NoMatch** 

Optional. Places an integer value in the result if a "no match" condition is found.


**StartPos** 

Optional. If the Start position is greater than 1, the result value is relative to the leftmost position in **BaseStr** , regardless of **StartPos** . Defaults to 1.


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - The specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


**Fnd** 

Optional. Is set if base string characters are not found in the comparator string. This indicator must be present if the **NoMatch** parameter is not present. Note that you can also use the [%FOUND](FOUND_Function.html) function.


**Type** 

Optional. Can be any of the Types listed. *NONE is the default. See [Type Parameter](Type_Parameter.html) for further information.


**Len** 

Optional. Defines the length of the field. If **Len** is decimal (3,1) *ZONED is assigned as the default. If **Len** is character (3), *CHAR is assigned as the default. 

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, types of *CHAR, *PACKED, *ZONED will require a **Len** . A compiler message will display if the **Len** parameter is needed.


### Remarks
Verification begins at the leftmost character of **BaseStr** and continues character by character left to right. Each character of **BaseStr** is compared with **CmpStr** characters. If a match is found in **BaseStr** , the next base string character is verified. If a "no match" condition is found, an integer value is placed in **NoMatch** to indicate the position of the incorrect character. 

**CHECK** stops checking when it finds the first incorrect character or when the end of **BaseStr** is reached. If no incorrect characters are found, **NoMatch** is set to zero. 

### Example

```
/* After the following example, N=6 and the found indicator 90 is on. Because the start 
position is 2, the first nonnumeric character found is the ".". */

Digits = "0123456789"
Salary = "$2000."
Check CmpStr(Digits) BaseStr(Salary) StartPos(2) Fnd(*In90)

/* Because F1 is a blank, **CHECK**  indicates the position of the first nonblank character. If STRING contains 
   "bbbASNA", NUM will contain the Value 4*/

STRING = // ASNA'
Check CmpStr(" ") BaseStr(String) NoMatch(Num) Fnd(*In90)

/* The following example checks that FIELD contains only the letters A to J. As a result, ARRAY=(136000) after the
 **CHECK** operation. Indicator 90 turns on.*/

DclArray Array 10 *ZONED Len(1,0)
Letter = "ABCDEFGHIJ"
Field = "1A=BC*"
Check Letter Field Array Fnd(*In90)

/* In the following example, because FIELD contains only the letters A to J, ARRAY=(000000). 
   Indicator 90 turns off since all characters are valid.*/

Field = "HIJHIJ" Check Letter Field Array Fnd(*In90)
```

### See Also
[CHECKR](CHECKR.html)
[%CHECK](CHECK_Function.html)
[%CHECKR](CHECKR_Function.html) 
