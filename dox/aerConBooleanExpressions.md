---
title: Boolean Expressions

Id: aerConBooleanExpressions
TocParent: aerConExpressions
TocOrder: 2


---

A **Boolean** expression is an expression that evaluates to a **Boolean** value. **Boolean** expressions can take several forms. The simplest is the direct comparison of the value of a **Boolean** variable to a **Boolean** literal, as shown in this example: 

```
If x = *True // Compares x to *True
            // Insert code to execute if x= *True
       Else // Insert code to execute if x= *False
EndIf
```

Note that the assignment statement ```x = True``` looks the same as the expression in the example, but it performs a different function and is used differently. In the above example, the expression ```x = True``` represents a value, and thus the ```=``` sign is interpreted as a comparison operator. In a stand-alone statement, it would be interpreted as an assignment operator and assign the value on the right to the variable on the left. The following example illustrates this: 

```
If x = *True  // Compare the value of x to *True
   y = *False // Assign *False to variable y
EndIf
```

Comparison operators, such as ```=, < , > , <> , <= ,``` and ```>=```, produce **Boolean** expressions by comparing the expression on the left side of the operator to the expression on the right side of the operator and evaluating the result as true or false. For instance: 

```
39 < 81   // Evaluates to *True
```

Comparison expressions can be combined using logical operators to produce more complex **Boolean** expressions. The following example demonstrates the use of comparison operators in conjunction with a logical operator: 

```
x > y And x < 5000
```

In the example, the value of the overall expression depends on the values of the expressions on each side of the ```*And``` operator. If both expressions are true, then the overall expression evaluates as ```*True```. If either expression is false, then the entire expression evaluates to ```*False```. 

### Parenthetical Expressions
You can use parentheses to control the evaluation of **Boolean** expressions. Expressions enclosed by parentheses evaluate first. For multiple levels of nesting, precedence is granted to the most deeply-nested expressions. Within parentheses, evaluation proceeds according to the rules of operator precedence. For more information, see [Operator Precedence in Encore RPG](Expression_Operators_and_their_Precedence.html). 

### See Also
[Logical Operators](aerConLogicalOperators.html)

[Assignment Op Codes](aerConAssignmentOpCodes.html) 
