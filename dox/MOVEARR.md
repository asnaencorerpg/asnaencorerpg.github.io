---
title: MOVEARR

Id: MOVEARR
TocParent: aerLrfOpCodesMain
TocOrder: 1220


---

Transfers character or numeric values from **Source** to the **Target** . **Source** and **Target** ** *must* ** be an array. 

```
 **MOVEARR
Source** (Expression) **Target**  (Character Expression)
Fill (<u>*NOPAD</u> | *PAD)
Pos (Indicator Variable)
Neg (Indicator Variable)
Boz (Indicator Variable)
Type (*BINARY | *BOOLEAN | *BYTE | *CHAR | *DATE | *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 | *IND | *INTEGER | *INTEGER2 | *INTEGER4 |
      *INTEGER8 | *ONECHAR | *PACKED | *TIME | *TIMESTAMP | *ZONED)
Len (Length Integer, [Decimal Integer])
```

### Parts

**Source** 

Required. If **Source** is longer than the **Target** , the excess rightmost characters are not moved. If the **Target** is longer than **Source** , the excess characters are left untouched, unless padding is specified. 

If **Source** is Character, then the **Target** also needs to be Character type. If **Source** is numeric, then the **Target** must also be numeric with the same format.


**Target** 

Required. If **Source** is longer than the **Target** , the excess rightmost characters are not moved. If the **Target** is longer than **Source** , the excess characters are left untouched unless padding is specified. 

If **Source** is Character, then the **Target** also needs to be Character type. If **Source** is numeric, then the **Target** must also be numeric with the same format.


**Fill** 

Optional. Specifies if you want to fill, or pad the **Target** with blanks. The default is *NOPAD. 

- *NOPAD indicates that the Target will not be padded with blanks.
- *PAD indicates that the Target will be padded with blanks.


**Pos** 

Optional. Turned on if the value of **Target** is a positive number.


**Neg** 

Optional. Turned on if the value of **Target** is a negative number.


**Boz**  [Blank or Zero]

Optional. Turned on if the value of **Target** is blank or zero.


**Type** 

Optional. Can be any of the Types listed (Character, Packed or Zoned). *NONE is the default. See [Type Parameter](Type_Parameter.html) for further information.


**Len** 

Optional. Defines the length of the field. If **Len** is decimal (3,1) *ZONED is assigned as the default. If **Len** is character (3), *CHAR is assigned as the default. 

Depending upon the **Type** specified, the **Len** parameter may be required. For instance, TYPES of *CHAR, *PACKED, *ZONED will require a **Len** . A compiler message will display if the **Len** parameter is needed.


### Remarks
Data is moved starting with the first element of an array if the array is not indexed; or, with the element specified if the array is indexed. Data stops moving when the last array element is moved or filled. 

A **P** specified in the operation extender position causes the **Target** to be padded on the right after the move occurs, if Source is shorter than the **Target** . 

### Example
<pre class="=prettyprint"><code class="language-aer">DclArray Arrx 5 *Char 2
DclArray Arry 6 *Char 2
DclArray Arrz 4 *Char 3 

 **Array-to-array move. No indexing; different length array, same element length.**  
 ARRX ARRY

|12|34|56|78|90| Before |AA|BB|CC|DD|EE|FF| 
  MoveArr Source(Arrx) Target(Arry) 
|12|34|56|78|90| After |12|34|56|78|90|FF| 

 **Array-to-array move with index Result Field.**  

 ARRX ARRY 
|12|34|56|78|90| Before |AA|BB|CC|DD|EE| 
  MoveArr Arrx Arry[3] 
|12|34|56|78|90| After |AA|BB|12|34|56| 

 **Array-to-array move, no indexing and different length array elements.** 

 ARRX ARRY 
|12|34|56|78|90| Before |AA|AB|BB|CC|CD|DD| 
  MoveArr Arrx Arry 
|12|34|56|78|90| After |12|34|56|78|90|DD| 

 **Array-to-array move, index Factor 2 with different length array elements.** 

 ARRX ARRZ 
|12|34|56|78|90| Before |AAA|BBB|CCC|DDD| 
  MoveArr Arrx[4] Arry 
|12|34|56|78|90| After |789|0BB|CCC|DDD| 

 **Field-to-array move, no indexing on array.** 

 FIELDA ARRY 
|1|2|3|4|5|6|7| Before |98|65|43|21|0A|BC| 
  MoveArr Fielda Arry) 
|1|2|3|4|5|6|7| After |12|34|56|71|0A|BC| 

 **In the following example, N=3. Array-to-field move with variable indexing.** 
 ARRX FIELD 
|01|0A|02|0B|03|0C| Before |0|1|0|A| 
  MoveArr Arrx[N] Field 
|01|0A|02|0B|03|0C| After |0|2|0|B| 

 **An array-to-array move showing numeric elements.** 

DclArray Arrb 4 *Packed Len(2,1)
DclArray Arrc 5 *Packed Len(2,1) 
|1.0 |1.1 |1.2 |1.3| Before |2.0 |3.0 |4.0 |5.0 |6.0| 
  MoveArr Arrb Arrc 
|1.0 |1.1 |1.2 |1.3| After |1.0 |1.1 |1.2 |1.3 |6.0| ```</pre>

### See Also
[DCLARRAY](DCLARRAY.html)

[MOVE](MOVE.html)

[MOVEL](MOVEL.html) 
