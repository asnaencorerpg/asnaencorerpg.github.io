---
title: DO

Id: DO
TocParent: aerLrfOpCodesMain
TocOrder: 690


---

Begins a group of operations and indicates the number of times the group will be processed. 

```
 **DO** 
FromVal (Numeric Variable)
ToVal (Numeric Variable)
Index (Character Expression)
Type (<u>*NONE</u> | *BINARY | *BOOLEAN | *BYTE | *CHAR | *FLOAT | *FLOAT4 | *FLOAT8 | *IND | *INTEGER | *INTEGER2 | 
      *INTEGER4 | *INTEGER8 | *ONECHAR | *PACKED | *ZONED)
Len (Length Integer, [Decimal Integer])
```

### Parts

**FromVal** 

Optional. Specify a starting value with zero decimal positions, using a numeric literal, named constant, or field name. If you do not specify this parameter, the starting value is 1.


**ToVal** 

Optional. Specify the limit value with zero decimal positions, using a numeric field name, literal, or named constant. If you do not specify this parameter, the limit value is 1.


**Index** 

Optional. Specify a numeric field name that will contain the current index value. The result must be large enough to contain the limit value plus the increment. If you do not specify an index field, one is generated for internal use. Any value in the index field is replaced by **FromVal** when the **DO** operation begins.


**Type** 

Optional. Can be any of the types listed (Character, Packed or Zoned). *NONE is the default. See [Type Parameter](Type_Parameter.html) for further information.


**Len** 

Optional. The **Len** parameter defines the length of the field. If **Len** is decimal (3,1) *ZONED is assigned as the default. If **Len** is character (3), *CHAR is assigned as the default. 

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, TYPES of *CHAR, *PACKED, *ZONED will require a **Len** . A compiler message will display if the **Len** parameter is needed.


### Remarks
The **DO** operation begins a group of operations and indicates the number of times the group will be processed. To indicate the number of times the group of operations is to be processed, specify an index field ( **Index** ), a starting value ( **FromVal** ), and a limit value ( **ToVal** ). An associated [ENDDO](ENDDO.html) statement marks the end of the group. 

The **DO** operation follows these 7 steps: 

1. If the conditioning indicators on the **DO** statement line are satisfied, the **DO** operation is processed (step 2). If the indicators are not satisfied, control passes to the next operation to be processed following the associated ENDDO statement (step 7).
2. The starting value ( **FromVal** ) is moved to the **Index** field when the **DO** operation begins.
3. If the index value is greater than the limit value, control passes to the calculation operation following the associated ENDDO statement (step 7). Otherwise, control passes to the first operation after the **DO** statement (step 4).
4. Each of the operations in the **DO** group is processed.
5. If the conditioning indicators on the ENDDO statement are not satisfied, control passes to the calculation operation following the associated ENDDO statement (step 7). Otherwise, the ENDDO operation is processed (step 6).
6. The ENDDO operation is processed by adding the increment to the index field. Control passes to step 3. **Note** the conditioning indicators on the **DO** statement are not tested again (step 1) when control passes to step 3.)
7. The statement after the ENDDO statement is processed when the index value is greater than the limit value (step 3).

### Example
/* The **DO** group is processed 10 times when indicator 17 is on; it stops running when the index value in field X, the **Index** , is greater than the limit value (10) in **ToVal** . When the **DO** group stops running, control passes to the operation immediately following the ENDDO operation. Because FromVal in the **DO** operation is not specified, the starting value is 1. Because **ToVal** of the ENDDO operation is not specified, the incrementing value is 1. */ 

```
If *In17 = *On 
 Do 1 10 X
  Y = Y + 1 
 Enddo
Endif
```

/* The **DO** group can be processed 10 times. The **DO** group stops running when the index value in field X is greater than the limit value (20) in ToVal. The starting value of 2 is specified in FromVal of the **DO** operation, and the incrementing value of 2 is specified in ToVal of the ENDDO operation. */ 

```

 Do 2 20 X
  Y = Y + 1
Enddo 2
```

### See Also
[DOUNTIL](DOUNTIL.html)
[ENDDO](ENDDO.html) 
