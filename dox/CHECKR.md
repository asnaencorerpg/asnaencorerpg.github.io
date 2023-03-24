---
title: CHECKR

Id: CHECKR
TocParent: aerLrfOpCodesMain
TocOrder: 280


---

Verifies from right to left that each character in a base string or array is among the characters in the comparator string. 

```

 **CHECKR
CmpStr**  (Character Expression)
 **BaseStr**  (Character Expression)
NoMatch (Numeric Variable)| <u>*NONE</u>)
StartPos (Numeric Expression) | <u>1</u>)
Err (Indicator Variable | *EXTENDED)
Fnd (Indicator Variable)
Type (<u>*NONE</u> | *BINARY | *BOOLEAN | *BYTE | *CHAR | *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 | *IND |
      *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *ONECHAR | *PACKED | *ZONED)
Len (Length Integer, [Decimal Integer])
```

### Parts

**CmpStr** 

Required. Verification begins at the rightmost character of **BaseStr** and continues character by character right to left. Each character of the base string is compared with **CmpStr** characters. If a match for a character in **BaseStr** exists in **CmpStr** , the next base string character is verified. If no match is found, an integer value is placed in **NoMatch** to indicate the position of the incorrect character. The position placed in **NoMatch** will be relative to the left, although checking is done from the right. **CmpStr** must be of the same type as **BaseStr** .


**BaseStr** 

Required. Must contain either the base string or the base string, followed by a colon, followed by the start location. The base string portion of **BaseStr** can contain: a field name, array element, named constant, data structure name, data structure subfield name, literal, or table name. The start location portion of **BaseStr** must be numeric with no decimal positions, and can be a named constant, array element, field name, literal, or table name. If no start location is specified, the length of the string is used. **BaseStr** must be of the same type as **CmpStr** .


**NoMatch** 

Optional. If not specified, you must specify the **Found** **Indicator** . It can be a numeric variable, numeric array element, numeric table name, or numeric array. Define the field or array specified with no decimal positions. 

If **NoMatch** is an array, the operation continues checking after the first incorrect character is found for as many occurrences as there are elements in the array. If there are more array elements than incorrect characters, all of the remaining elements are set to zeros. **CmpStr** must be a string and can contain one of: a field name, array element, named constant, data structure name, data structure subfield, literal, or table name. 

Figurative constants cannot be used in the **CmpStr** , **BaseStr** , or **NoMatch** . No overlapping is allowed in a data structure for **CmpStr** and **NoMatch** , or for **BaseStr** and **NoMatch** .


**StartPos** 

Optional. Defaults to the length of the string.


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - The specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - A program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


**Fnd** 

Optional. Is set if base string characters are not found in the comparator string. This indicator must be present if the **NoMatch** parameter is not present. Note that you can also use the [%FOUND](FOUND_Function.html) function.


**Type** 

Optional. Can be any of the types listed. *NONE is the default. See [Type Parameter](Type_Parameter.html) for further information.


**Len** 

Optional. Defines the length of the field. If **Len** is decimal (3,1) *ZONED is assigned as the default. If **Len** is character (3), *CHAR is assigned as the default. 

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, types of *CHAR, *PACKED, *ZONED will require a **Len** . A compiler message will display if the **Len** parameter is needed.


### Example

```
  /* Because Factor 
	1 is a blank character, CHECKR indicates the position of the first nonblank 
	character. This use of CHECKR allows you to determine the length of a string. 
	If String contains "ABCDEF ", Num will contain the value 6. */

 Checkr Cmpstr(" ") Basestr(String) NoMatch(Num)      

 /* After the following example, N=1 and the 
	found indicator 90 is on. Because the start position is 5, the operation begins 
	with the rightmost 0 and the first nonnumeric found is the "$". */

 DclConst Digits "0123456789"
	 Salary = "$2000."
	 Checkr Cmpstr(Digits) Basestr(Salary) 
	 NoMatch(N) Startpos(5) +
	 Fnd(*In90)

 /* The following example checks that field 
	contains only the letters A to J. As a result, array=(876310) after the
	CHECKR operation. Indicator 90 turns on. */

 DclArray Array DCLFLD(6) Len(1,0)
	 DclConst Letter "ABCDEFGHIJ"
	 DclFld Field *CHAR Len(8)
	 Field = "1A=BC***"Checkr Cmpstr(Letter) Basestr(Field) 
	 NoMatch(Array) Err (*In90)      
```

### See Also
[CHECK](CHECK.html)
[%CHECK](CHECK_Function.html)
[%CHECKR](CHECKR_Function.html) 
