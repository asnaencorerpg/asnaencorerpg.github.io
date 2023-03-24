---
title: CASEDFT

Id: CASEDFT
TocParent: aerLrfOpCodesMain
TocOrder: 230


---

Specifies the default subroutine to be run in a [CASE](CASE.html) group.

```

 **CASEDFT** 
 **Sr**  (Subroutine Name)<br />ParmList (<u>*NONE</u> | Subroutine Name)<br /> **F1**  (Operand)
 **F2**  (Operand)<br />Hi (Indicator Variable)<br />Lo (Indicator Variable)<br />Eq (Indicator Variable)
```

### Parts

**Sr** 

Required. Contains the subroutine name to be called. The name must be a valid subroutine name declared on a [BEGSR](BEGSR.html) command. ****


**ParmList** 

Optional. The name of the parameter list. *NONE is the default.


**F1** 

Optional. Can contain any valid operation.


**F2** 

Optional. Can contain any valid operation.


**Hi** 

Optional. As a result of the comparison, the **Hi** indicator is set on if **F1** is greater than **F2** .


**Lo** 

Optional. As a result of the comparison, the **Lo** indicator is set on if **F1** is less than **F2** .


**Eq** 

Optional. As a result of the comparison, the **Eq** indicator is set on if **F1** is equal to **F2** .


### Remarks
The **CASEDFT** operation is functionally identical to an [EXSR](EXSR.html) operation. Any **CASE** operations that follow an unconditional **CASEDFT** operation in the same **CASE** group are never tested. The normal placement of the unconditional **CASEDFT** operation is after all other **CASE** operations. 

### See Also
[BEGSR](BEGSR.html)
[CASE](CASE.html)
[ENDCS](ENDCS.html)
[EXSR](EXSR.html) 
