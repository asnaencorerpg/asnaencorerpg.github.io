---
title: "*As Operator"

Id: As_Operator
TocParent: aerLrfOperatorsMain
TocOrder: 6


---

The * **AS** operator is used to perform conversions between compatible types. The * **AS** operator is used in an expression of the form: 

```
 *expression* 
 **as** 
 *type* 
```

where: 

*expression* 

An expression of a reference type.


*type* 

A reference type.


### Remarks
The ***AS** operator is similar to a cast, except that it yields null on conversion failure instead of raising an exception. 

The * **AS** operator only performs reference conversions. The * **AS** operator cannot perform other conversions, such as user-defined conversions, which should instead be performed using cast expressions. 

### See Also
[Operators](aerLrfOperatorsMain.html)
[Operators and Their Precedence](Expression_Operators_and_their_Precedence.html) 
