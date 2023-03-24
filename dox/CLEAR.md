---
title: CLEAR

Id: CLEAR
TocParent: aerLrfOpCodesMain
TocOrder: 290


---

Sets elements in a structure (record format, data structure, array, table or a form) or a variable (field, subfield, property or indicator), to zero, blank or "0", depending on field type (numeric, character, or indicator). It allows you to clear structures on a global basis, as well as element by element, during run-time. 

```
 **CLEAR
Result**  (Value)
Exclude (*<u>NONE</u> | *NOKEY)
Occurance (<u>*CURRENT</u> | *ALL | *RECORDS)
Type (<u>*NONE</u>| *BINARY | *BOOLEAN | *BYTE | *CHAR | *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 | *IND |
      *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *ONECHAR | *PACKED | *ZONED)
Len (Length Integer, [Decimal Integer]
```

### Parts

**Result** 

Required. Contains the elements to clear.


**Exclude** 

Optional. Must be *NONE or not given unless **Occurance** contains a DISK record format name; in which case, it can contain *NOKEY to indicate that all fields except key fields are to be cleared.


**Occurrance** 

Optional. Valid only if the **Result** is a table, a record format, or a multiple occurrence data structure. *CURRENT is the default. 

- If *CURRENT (or nothing) is given, only the current occurrence will be cleared.
- If *ALL is given, all occurrences will be cleared.
- *RECORDS is only valid when clearing a subfile, and it means that the records will be removed from the subfile. If *RECORDS is not specified for a subfile, the subfile record format will be cleared in the same manner as any other file.
- If you have partially overlapping fields of different definitions, data that is not valid could exist in numeric fields.
- If you specify an array name, the entire array is cleared. If you specify an array element (including indicators) in factor 2 using an array index, only the element specified is cleared.


**Type** 

Optional. Can be any of the types listed. *NONE is the default. See [Type Parameter](Type_Parameter.html) for further information.


**Len** 

Optional. Defines the length of the field. If **Len** is decimal (3,1) *ZONED is assigned as the default. If **Len** is character (3), *CHAR is assigned as the default. 

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, types of *CHAR, *PACKED, *ZONED will require a **Len** . A compiler message will display if the **Len** parameter is needed.


### Remarks
Time/Date/TimeStamp fields will be set to a default value depending on their type equal to 0001-01-01.00.00.00.000000. 

Any property can be cleared, and any control that has a default property can be cleared. The default values work as follows: 

- Numeric properties: set to 0.
- String properties:    set to the empty string.
- Picture properties:   set to no picture.
- Boolean properties: set to False (*OFF).
- Date properties:      set to
                0001-01-01-00.00.00.000000

### See Also
[WRITE](WRITE.html) 
