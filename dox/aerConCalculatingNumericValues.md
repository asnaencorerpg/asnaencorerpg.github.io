---
title: Calculating Numeric Values

Id: aerConCalculatingNumericValues
TocParent: aerConExpressions
TocOrder: 0


---

Numeric values can be calculated through the use of numeric expressions. A numeric expression is an expression that contains literals and variables representing numeric values, and operators that act upon those values. The following is an example of a numeric expression: 

<code class="language-aer">4 * (67 + x) // For the purposes of this example, x = 2.``` 

This expression evaluates to ```276```, which is the value of 67 plus 2, multiplied by 4. 

If the numeric expression contains more than one operator, the order in which they are evaluated is determined by the rules of operator precedence. To override the rules of operator precedence, you enclose calculating numeric values in parentheses, as in the above example; such calculating numeric values are evaluated first. For more information, see [Operator Precedence in Encore RPG.](Expression_Operators_and_their_Precedence.html) 

You can use an assignment statement to assign the value represented by this expression to another variable, as in this example: 

```
DCLFLD x Type (*Integer) Len (4)
   x = 2
DCLFLD y Type (*Integer) Len (4) 
   y = 4 * (67 + x)
```

Here, the value of the expression on the right side of the operator is assigned to the variable <code class="ce">y``` on the left side of the operator, so <code class="ce">y``` evaluates to ```276```. For more information on assignment, see [Assignment Statements](aerConAssignmentOpCodes.html). 

### See Also
[Assignment Statements](aerConAssignmentOpCodes.html)
[Value Comparisons](aerConValueComparisons.html)
[Assignment Statements](aerConAssignmentOpCodes.html)
[Operator Precedence in Encore RPG](Expression_Operators_and_their_Precedence.html) 
