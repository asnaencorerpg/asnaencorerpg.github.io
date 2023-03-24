---
title: Type Conversions

Id: Type_Conversions
TocParent: aerLrfLangElementsMain
TocOrder: 11


---

**Indicator Conversions:** 

A single character "1" moved to an indicator variable sets the indicator to the *ON value, and a single character "0" moved to an indicator variable sets the indicator to the *OFF value. Likewise, a move from an indicator variable to a character variable sets the first byte of the character variable to a "1" or "0". 

**Numeric Conversions:** 

Numeric operands are promoted to a zoned number before being used on any operation. If all the operands involved are binary with the same specification, the promotion may be virtual. 

**Implicit Conversions:** 

Implicit Conversions are done when two operands in an expression are not of the same type. These conversions can only be done implicitly if the operands are both character or indicator, or are both numerics. Character or indicator operands mixed with numeric operands will result in a compiler error. 

### Related Sections
[Commands](Commands.html) 

[Expressions](Expressions.html) 

[Simple Types](Simple_Types.html) 

### See Also
[Language Elements](aerLrfLangElementsMain.html)
[Encore RPG Language Reference](aerLrfLangRefMain.html)
[Syntactical Elements](aerLrfSyntacticalElementsMain.html) 
