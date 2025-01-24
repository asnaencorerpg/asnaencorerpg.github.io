---
title: SUBST Function

Id: SUBST_Function
TocParent: Functions_overview
TocOrder: 44


---

<span style="FONT-WEIGHT: bold">%SUBST</span> [built-in function](Functions_overview.html) returns a portion of argument string. It may also be used as the result of an assignment with the [EVAL](EVAL.html) operation code. 

```
%SUBST (String, Start  {Length})
```

### Parameters

**String** 

Required. Must be character. Starting position and length may be any numeric value or numeric expression with zero decimal positions. When the string parameter is of varying length, the values of the other parameters are checked against the current length, not the maximum length.


**Start** 

Required. Represents the starting position of the substring. The starting position must be greater than zero.


**Length** 

Optional. Represents the length of the substring. If it is not specified, the length is the length of the string parameter less the start value plus one. The length may be greater than or equal to zero.


### Remarks
When specified as a parameter for a definition specification keyword, the
        parameters must be literals or named constants representing literals. 
        When specified on a free-form calculation specification, the parameters may be
        any expression.

### Example

```
BEGSR Subst_Ex
   DclConst Name(City) Value("San Antonio")

ioField1.Text = %Subst(City, 5, 7)
ENDSR
```

### See Also
[Built-in Function Overview](Functions_overview.html)<br />
            [EVAL](EVAL.html)

