---
title: Expression Operators and their Precedence

Id: Expression_Operators_and_their_Precedence
TocParent: Expressions
TocOrder: 1


---

The following are the valid operators for expressions listed in order of precedence from *highest to lowest.<br />* 

| Precedence   | **Expression** | **Description**  |
| ------------ | -------------- | ---------------- |
| **1.** | Unary - <br> Unary + <br/> ~, *NOT  | - Makes a negative number <br/> Provides an explicit sign <br/>Not Condition 
| **2.** | [**](StarStar_Op.html) | Exponent 
| **3.** | [*](Multiply_Operator.html) <br/> [/](Divide_Operator.html) | Multiply <br/> Divide 
| **4.** | [+](Plus_Operator.html) <br/> - | Add <br/> Subtract
| **5.** | <, *LT <br/> >, *GT <br/> <=, *LE <br/> >=, *GE <br/>=, *EQ <br/> <>, *NE | Less Than <br/> Great Than <br/> Less Than or Equal To <br/> Greater Than or Equal To <br/> Equal Condition <br/> Not Equal Condition <br/>
| **6.** | &, *AND | And Condition 
| **7.** | &#124;, *OR | Or Condition 

Any number of parentheses ( ) can be used to force the precedence of any operator. The deepest levels of parentheses will be evaluated first, until the whole expression is evaluated. 

All of the mathematical operands, such as -, +, /, *, and ** are valid only for numeric values, except for the "+". The "+" will also do a concatenate if the two operands are character strings. 


### See Also
[Operators](aerLrfOperatorsMain.html)
[Comparison Operators](Comparison_Operators.html) 
