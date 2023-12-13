---
title: OCCUR

Id: OCCUR
TocParent: aerLrfOpCodesMain
TocOrder: 1270


---

Sets and/or gets the current occurrence of a data structure that is to be used for the next access to the data structure or data structure subfield. 

```
OCCUR 
 Ds  (Data Structure)
NewIndex (<u>*NONE</u> | Numeric Expression, Numeric Expression,...)
OldIndex (<u>*NONE</u> | Character Expression)
Err (Indicator Variable | *EXTENDED)
Type (<u>*NONE</u> | *BINARY | *BOOLEAN | *BYTE | *CHAR | *FLOAT | *FLOAT4 | *FLOAT8 | *IND | 
      *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *ONECHAR | *PACKED | *ZONED)
Len (Length Integer, [Decimal Integer]      
```

### Parts

**Ds** 

Required. Contains the name of the Data Structure. If the data structure has multiple occurrences or a subfield of that data structure is specified in an operation, the first occurrence of the data structure is used until an **OCCUR** operation is specified. After **OCCUR** is specified, the occurrence of the data structure that was established by **OCCUR** is used.


**NewIndex** 

Required only if **OldIndex** is not specified; optional if **OldIndex** is specified. Use to specify a new current occurrence for the data structure. The current occurrence is relative to zero. 

**Please note** that either the **NewIndex** or **OldIndex** parameter is required.


**OldIndex** 

Required only if **NewIndex** is not specified; optional if **NewIndex** is specified. Use as a receiver of the current index before a new index is set. If the data structure has multiple dimensions, a value must be provided for each dimension of both the old and new occurrence values. The current occurrence is relative to zero. 

An alternate way to access occurrences is by using the [] operators. See [Multiple Occurrence Data Structures](Mult_Occur_DS.html).


**Please note** that either the **OldIndex or NewIndex** parameter is required.


**Err** 

Optional. Determines what the runtime will do if an error occurs while executing this command. The following rules apply: 

- **Err** (Indicator Variable) - the specified Indicator is set if an error occurred.
- **Err** (*EXTENDED) - a program status flag is set whose status can be checked using the [%ERROR](ERROR_Function.html) built-in function.
- If the **Err** keyword is not given and an error occurs, a runtime exception will be thrown.


**Type** 

Optional. Can be any of the Types listed (Character, Packed or Zoned). *NONE is the default. See [Type Parameter](Type_Parameter.html) for further information.


**Len** 

Optional. Defines the length of the field. If **Len** is decimal (3,1) *ZONED is assigned as the default. If **Len** is character (3), *CHAR is assigned as the default. 

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, Types of *CHAR, *PACKED, *ZONED will require a **Len** . A compiler message will display if the **Len** parameter is needed.


### Remarks
All data structures (and arrays) in Encore RPG are **zero-based** . 

### Example

```
DclDs LastYear DCLFLD(50)
  DclDsFld SalesLy Len(10)
  DclDsFld ReturnsLy Len(10)

  DclDs ThisYear DCLFLD(50)
  DclDsFld SalesTy Len(10)
  DclDsFld ReturnsTy Len(10) 

LASTYEAR is set to the third occurrence. The subfields SALESLY and RETURNSLY of the third occurrence can now be used. 
The ZADD operations change the contents of SALESLY and RETURNSLY, respectively, in the third occurrence of LASTYEAR. 

  Occur LastYear 3
  SalesLy = TotalSales
  ReturnsLy = TotalReturns 

LASTYEAR is set to the fourth occurrence. Using the values in SALESLY and RETURNSLY of the fourth occurrence of LASTYEAR,
the ZADD operation places the contents of SALESLY in the Result Field, SALES, and the ZADD operation places the contents
of RETURNSLY in the Result Field, RETURNS. 

  Occur LastYear 4
  Sales = SalesLy
  Returns = ReturnsLy 
LASTYEAR is set to the occurrence specified in field Index. For example, if Index = 10, LASTYEAR is set to the tenth occurrence. 

  Occur LastYear Index 

LASTYEAR is set to the current occurrence of THISYEAR. For example, if the current occurrence of THISYEAR is the twelfth 
occurrence, LASTYEAR is set to the twelfth occurrence. 

  Occur LastYear ThisYear 

The value of the current occurrence of LASTYEAR is placed in the Result Field, Z. Field Z must be numeric with zero decimal
positions. For example, if the current occurrence of LASTYEAR is 15, field Z contains the value 15. 

  Occur Z LastYear 

LASTYEAR is set to the current occurrence of THISYEAR. The value of the current occurrence of LASTYEAR is then moved to the
Result Field, Z. For example, if the current occurrence of THISYEAR is the fifth occurrence, LASTYEAR is set to the fifth 
occurrence. The Result Field, Z, contains the value 5. 

  Occur DS(LastYear) NewIndex(ThisYear) OldIndex(Z) Err (*In20) 

LASTYEAR is set to the current occurrence of Index. For example, if Index = 15, LASTYEAR is set to the fifteenth occurrence.
If Index equals 0 or is greater than 50, an error occurs, and indicator 20 is set on. If indicator 20 is on, the LR indicator 
is set on. 

  Occur Ds(LastYear) NewIndex(Index) OldIndex(Z) Err (*In20)
  If *In20
  *InLr = *On
  Endif 
  DclDs LastYear DCLFLD(50)
  DclDsFld SalesLy Len(10)
  DclDsFld SalesByMonthLy DCLFLD(12) Len(10,0)
  DclDsFld ReturnsLy len(10)
  DclDsFld ReturnsByMonthLy DCLFLD(12) Len(10,0)

  DclDs ThisYear DCLFLD(50)
  DclDsFld SalesTy Len(10)
  DclDsFld SalesByMonthTy DCLFLD(12) Len(10,0)
  DclDsFld ReturnsTy len(10)
  DclDsFld ReturnsByMonthTy DCLFLD(12) Len(10,0) 

LASTYEAR is set to the third occurrence. The subfields SALESLY and RETURNSLY of the third occurrence can now be used.
The ZADD operations change the contents of SALESLY and RETURNSLY, respectively, in the third occurrence of LASTYEAR.
Also the monthly elements of both Sales and Returns are moved in an array of 12 each. 

  Occur LastYear 3
  SalesLy = TotalSales
  ReturnsLy = TotalReturns
  SalesMonthLyArray = SalesByMonthLy
  ReturnMonthLyArray = ReturnsByMonthLy 
```

### See Also
[DCLDS](DCLDS.html)

[DCLDSFLD](DCLDSFLD.html)

[Multiple Occurrence Data Structures](Mult_Occur_DS.html)

[%OCCUR](OCCUR_Function.html) 
