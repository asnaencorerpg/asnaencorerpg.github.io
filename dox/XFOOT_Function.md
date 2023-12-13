---
title: "%XFOOT_Function"

Id: XFOOT_Function
TocParent: Functions_overview
TocOrder: 51


---

<span style="FONT-WEIGHT: bold">%XFOOT</span> [built-in function](Functions_overview.html) results in the sum of all elements of the specified, single-dimensioned numeric array expression. 

```
%XFOOT 
 (array-expression) 
        
```

### Parts

**array-expression** 

Required. The precision of the result is the minimum that can hold the result of adding together all array elements, up to a maximum of 28 digits. The number of decimal places in the result is always the same as the decimal places of the array expression. 

For example, if ARR is an array of 500 elements of precision (17,4), the result of **%XFOOT** (ARR) is (20,4). 

For **%XFOOT** (X) where X has precision (m,n), the following table shows the precision of the result based on the number of elements of X: 

Elements of X Precision of **%XFOOT** (X)
<pre>1 (m,n) 
2-10 (m+1,n) 
11-100 (m+2,n) 
101-1000 (m+3,n) 
1001-10000 (m+4,n) 
10001-32767 (m+5,n) </pre>


### Remarks
Normal rules for array expressions apply. For example, if ARR1 has 10 elements and ARR2 has 20 elements, **%XFOOT** (ARR1+ARR2) results in the sum of the first 10 elements of ARR1+ARR2. 

This built-in function is similar to the **XFOOT** operation, except that float arrays are summed like all other types, beginning from index 0 on up. 

### Example

```

// MyArray Values are 1.064, 1.703, -1.110.

  DclArray MyArray 3 *PACKED Len(4,3)
  DclFld MyArraySum *PACKED Len(5,2)
  MyArraySum = %XFoot(MyArray)

// To Round up:

  Eval (MyArraySum = %Xfoot(MyArray)) Adj(*Rndup)
```

### See Also
[Built-in Function Overview](Functions_overview.html)

[XFOOT Operation](XFOOT.html) 
