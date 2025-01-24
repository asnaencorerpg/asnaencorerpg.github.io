---
title: COMPARE

Id: COMPARE
TocParent: aerLrfOpCodesMain
TocOrder: 320


---

Compares **F1** with **F2** and places the result of the comparison in the resulting indicators. 

```
COMPARE
F1  (Operand)
 F2  (Operand)
Hi (Indicator Variable)
Lo (Indicator Variable)
Eq (Indicator Variable)
```

### Parameters

**F1** 

Required. Can contain any valid [Operand](Operands.html).


**F2** 

Required. Can contain any valid Operand.


**Hi** 

Optional. As a result of the comparison, the **Hi** indicator is set on if **F1** is greater than **F2** .


**Lo** 

Optional. As a result of the comparison, the **Lo** indicator is set on if **F1** is less than **F2** .


**Eq** 

Optional. As a result of the comparison, the **Eq** indicator is set on if **F1** is equal to **F2** .


### Remarks
You must specify at least one resulting indicator. Do not specify the same indicator for all three conditions. When specified, the resulting indicators are set On or Off (for each cycle) to reflect the results of the compare. 

### Example

```
/* Initial values are :

    ShirtsLong = 100
    ShirtsShort = 105
    PullOvers = 100
    OnOrder = MasterOnOrder
    ItemSold = MasterSold */

//Indicator 12 is set on. Indicators 11 and 13 are set off.

    Compare ShirtsLong ShirtsShort Hi(*In11) Lo(*In12) Eq(*In13)

// Indicator 15 is set on; indicator 14 is set off.

    Compare	ShirtsLong ShirtsShort Hi(*In14) Lo(*In15) Eq(*In14)

// Indicator 18 is set on; indicator 17 is set off.

    Compare	ShirtsLong PullOvers Hi(*In17) Lo(*In17) Eq(*In18)

//Indicator 21 is set on; indicators 20 and 22 are set off.

    Compare	OnOrder ItemSold Hi(*In20) Lo(*In21) Eq(*In22)      
```

### See Also
[Operands](Operands.html) 
