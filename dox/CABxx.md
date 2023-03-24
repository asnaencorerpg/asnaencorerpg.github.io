---
title: CABXX

Id: CABxx
TocParent: aerLrfOpCodesMain
TocOrder: 180


---

Compares F1 with F2 according to the condition given by <code> **Relop** </code>, and branches to the location specified in <code> **Label** </code>. 

```

 **CABXX** 
F1 (Operand)<br />Relop (Comparison Operator)
 **F2**  ( **Operand**  )
Label  (Label)<br />Hi (Indicator Variable)
Lo (Indicator Variable)
Eq (Indicator Variable) 
```

### Parts

**F1** 

Optional. Must contain a valid operand.


<code> **Relop** </code>

Optional. A comparison operator that must be one of the accepted ECR relational operators, such as <code>&gt;, =, *NE, *GT</code>, etc.


**F2** 

**Required** . Must contain a valid operand.


<code> **Label** </code>

Optional. A name specified in a program that can allow commands to be the target of a <code> **GOTO** </code> command.


<code> **Hi** </code>

Optional. As a result of the comparison, the <code> **Hi** </code> indicator is set on if **F1** is greater than **F2** .


<code> **Lo** </code>

Required. As a result of the comparison, the <code> **Lo** </code> indicator is set on if **F1** is less than **F2** .


<code> **Eq** </code>

Optional. As a result of the comparison, the <code> **Eq** </code> indicator is set on if **F1** is equal to **F2** .


### Remarks
The <code> **CABXX** </code> operation is functionally identical to a <code> **GOTO** </code> operation. 

### See Also
[GOTO](GOTO.html) 
