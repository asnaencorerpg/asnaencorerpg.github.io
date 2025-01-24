---
title: FOREACH

Id: FOREACH
TocParent: aerLrfOpCodesMain
TocOrder: 1100


---

Iterates over a group of statements, once for each element in an array or a collection. **FOREACH** is used to iterate through the array or collection to get the desired information, but should not be used to change the contents of the array or collection to avoid unpredictable side effects. The statements that constitute the body of the **FOREACH** are those that follow the **FOREACH** declaration up to the first ENDFOR found. 

```
FOREACH
Name  (Field name)
 Collection  (Expression)
Type (*BINARY | *BOOLEAN | *BYTE | *CHAR | *DATE | *DECIMAL | *FLOAT | *FLOAT4 | *FLOAT8 | *IND |
     *INTEGER | *INTEGER2 | *INTEGER4 | *INTEGER8 | *OBJECT | *ONECHAR | *PACKED | *STRING | *TIME | *TIMESTAMP | *ZONED)
Len (Integer Literal, Integer Literal)
```

### Parameters

**Name** 

Required. The name of the field that holds the current iteration element of the array or collection. Its type must match the types of the elements in the array or collection.


**Collection** 

Required. Expression that evaluates to a collection (an object whose type implements IEnumerable) or an array.


**Type** 

Optional. **Type** can be any of the "*" Types list. If **Type** is not specified, the **Len** specified determines the default.


- **Type** cannot be a named constant or a literal.
- If **Type** is an array, array element, or a table name, the attributes of an element of the array or table are used to define the field.
- If a **Type** parameter is not given, the **Len** parameter is required. In this case, *CHAR is assumed if there is one integer, and *ZONED is assumed if there are two integers.


**Len** 

Optional. **Len** specifies the length of the field. If **Len** is decimal e.g. Len (3,1) *ZONED is assigned as the default. If **Len** is character e.g. **Len** (3), *CHAR is assigned as the default. 

If **Type** is packed, then the length is not the number of bytes the packed field fits into, but rather the logical digit length of the field. For example, if you want a 7 digit packed with 2 decimals, code **Len** (7,2).


**Remarks** 

The embedded statements continue to execute for each element in the array or collection. After the iteration has been completed for all the elements in the collection, control is transferred to the next statement following the **FOREACH/ENDFOR** block. 

**Example** 

In this example, we iterate over the Controls collection of a GroupBox control, finding all the buttons and setting their captions. 

```
ForEach name( mybtn ) collection( groupBox1.Controls ) type( Button )
  myBtn.Text = "This is Button " + count.ToString()
  count = count + 1
EndFor      
```

### See Also
[DCLARRAY](DCLARRAY.html)

[ENDFOR](ENDFOR.html) 
