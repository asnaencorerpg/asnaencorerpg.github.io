---
title: CASXX

Id: CASxx
TocParent: aerLrfOpCodesMain
TocOrder: 240


---

Allows you to conditionally select a subroutine for processing.

```
 **CASxx** 
F1 (Operand)
Relop (Comparison Operator)
F2 (Operand)
 **Sr (Subroutine Name)** ParmList (Parameter List)
Hi (Indicator Variable)
Lo (Indicator Variable)
Eq (Indicator Variable) 
```

### Parts

**F1** 

Optional. Must contain a valid operand.


**Relop** 

Optional. A comparison operator that must be one of the accepted ECR relational operators, such as &gt;, =, *NE, *GT, etc.


**F2** 

Optional. Must contain a valid operand.


**Sr** 

**Required** . Contains the subroutine name to be called. The name must be a valid subroutine name declared on a [BEGSR](BEGSR.html) command.


**Parmlist** 

Optional. The name of the parameter list.


**Hi** 

Optional. As a result of the comparison, the **Hi** indicator is set on if **F1** is greater than **F2** .


**Lo** 

Required.As a result of the comparison, the **Lo** indicator is set on if **F1** is less than **F2** .


**Eq** 

Optional. As a result of the comparison, the **Eq** indicator is set on if **F1** is equal to **F2** .


### Remarks
The **CASxx** operation is functionally identical to a **CASEDFT** operation when the **F1** , **Relop** , and **F2** keywords are not used. 

CASXX is similar to the ECR Classic CASxx, except that RELOP is now conditional and must be one of the accepted ECR relational operators, such as &gt;, =, *NE, *GT, etc. Also,the **Parmlist** parameter was added to allow the passing of arguments to the subroutine. 

### See Also
[BEGSR](BEGSR.html)
[CASEDFT](CASEDFT.html)
[COMP](COMPARE.html) 
