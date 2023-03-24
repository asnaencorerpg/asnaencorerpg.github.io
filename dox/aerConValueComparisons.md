---
title: Value Comparisons

Id: aerConValueComparisons
TocParent: aerConExpressions
TocOrder: 1


---

Comparison operators can be used to construct expressions that compare the values of numeric variables. These expressions return a **Boolean** value based on whether the comparison is true or false. Examples of such an expression would be: 

```
88 > 76
34 > 55
```

The first expression evaluates to ``` **True** ```, because 88 is greater than 76. The second example evaluates to ``` **False** ```, because 34 is not greater than 55. 

You can compare any two numeric expressions in this fashion. The expressions you compare can themselves be complex expressions, as in this example: 

```
x / 55 * (y +11) >= System.Math.Sqrt(z) / (p - (x * 16))
```

This complex expression includes literals, variables, and function calls. The expressions on both sides of the comparison operator are evaluated, and the resulting values are then compared using the ``` **>=** ``` comparison operator. If the value of the expression on the left side is greater than or equal to the value of the expression on the right, the entire expression evaluates to ``` **True** ```; otherwise, it evaluates to ``` **False** ```. 

Expressions that compare values are most commonly used in ``` **If...Then** ``` statements, as in the following example: 

```
If x > 30 Then
   // Insert code to be executed if x is greater than 30.
Else
   // Insert code to be executed if x is less than or equal to 30.
End If
```

The ``` **=** ``` sign is a comparison operator as well as an assignment operator. When used as a comparison operator, it evaluates whether the value on the left is equal to the value on the right, as shown in the following example: 

```
If x = 30
   Then // Insert code to continue program. 
EndIf
```

You can also use a comparison expression anywhere that a **Boolean** value is needed such as in an ``` **If** , **While** , **Loop** , **ElseIf** ``` command or when assigning to or passing avalue to a boolean variable. In the following example, the value returned by the comparison expression is assigned to a **Boolean** variable: 

```
DclFld x *As (*Boolean)
x = 55 < 30   // x is assigned False.
```

### See Also
[Boolean Expressions](aerConBooleanExpressions.html)
[Operators](aerConOperators.html)
[Comparison Operators](aerConComparisonOperators.html)
[Expressions](aerConExpressions.html) 
