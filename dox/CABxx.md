---
title: CABXX

Id: CABxx
TocParent: aerLrfOpCodesMain
TocOrder: 180


---

Compares F1 with F2 according to the condition given by ```Relop```, and branches to the location specified in ```Label```. 

```
CABXX 
F1 (Operand)
Relop (Comparison Operator)
 F2  ( Operand  )
Label  (Label)
Hi (Indicator Variable)
Lo (Indicator Variable)
Eq (Indicator Variable) 
```

### Parameters

**F1** 

Optional. Must contain a valid operand.


```Relop```

Optional. A comparison operator that must be one of the accepted ECR relational operators, such as ```>, =, *NE, *GT```, etc.


**F2** 

**Required** . Must contain a valid operand.


```Label```

Optional. A name specified in a program that can allow commands to be the target of a ```GOTO``` command.


```Hi```

Optional. As a result of the comparison, the ```Hi``` indicator is set on if **F1** is greater than **F2** .


```Lo```

Required. As a result of the comparison, the ```Lo``` indicator is set on if **F1** is less than **F2** .


```Eq```

Optional. As a result of the comparison, the ```Eq``` indicator is set on if **F1** is equal to **F2** .


### Remarks
The ```CABXX``` operation is functionally identical to a ```GOTO``` operation. 

### See Also
[GOTO](GOTO.html) 
