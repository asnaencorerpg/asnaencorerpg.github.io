---
title: "%FLOAT Function"

Id: FLOAT_Function
TocParent: Functions_overview
TocOrder: 20


---

<span style="FONT-WEIGHT: bold">%FLOAT</span> [built-in function](Functions_overview.html) converts the value of the numeric expression to float format. 

```

 **%FLOAT (NumericExpression)** 
```

### Parts

**NumericExpression** 

Required. The numeric expression to convert.


### Remarks
This built-in function may only be used in expressions. 

### Example

```
   BEGSR Float_Ex
	DclFld Name(A) Type(*PACKED) Len(1,0)
	DclFld Name(B) Type(*PACKED) Len(1,0)
	DclFld Name(Result)    Type(*PACKED) Len(6,5)
	A= 1
	B = 3 
    	The value of "Result" is now 0.33333
    ENDSR 
```

### See Also
[Built-in Function Overview](Functions_overview.html) 
