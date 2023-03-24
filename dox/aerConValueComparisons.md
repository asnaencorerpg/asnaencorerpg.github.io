---
title: Value Comparisons

Id: aerConValueComparisons
TocParent: aerConExpressions
TocOrder: 1


---

Comparison operators can be used to construct expressions that compare the values of numeric variables. These expressions return a **Boolean** value based on whether the comparison is true or false. Examples of such an expression would be: 

```
88 &gt; 76
34 &gt; 55
```

The first expression evaluates to <code> **True** </code>, because 88 is greater than 76. The second example evaluates to <code> **False** </code>, because 34 is not greater than 55. 

You can compare any two numeric expressions in this fashion. The expressions you compare can themselves be complex expressions, as in this example: 

```
x / 55 * (y +11) &gt;= System.Math.Sqrt(z) / (p - (x * 16))
```

This complex expression includes literals, variables, and function calls. The expressions on both sides of the comparison operator are evaluated, and the resulting values are then compared using the <code> **&gt;=** </code> comparison operator. If the value of the expression on the left side is greater than or equal to the value of the expression on the right, the entire expression evaluates to <code> **True** </code>; otherwise, it evaluates to <code> **False** </code>. 

Expressions that compare values are most commonly used in <code> **If...Then** </code> statements, as in the following example: 

```
If x &gt; 30 Then
   // Insert code to be executed if x is greater than 30.
Else
   // Insert code to be executed if x is less than or equal to 30.
End If
```

The <code> **=** </code> sign is a comparison operator as well as an assignment operator. When used as a comparison operator, it evaluates whether the value on the left is equal to the value on the right, as shown in the following example: 

```
If x = 30
   Then // Insert code to continue program. 
EndIf
```

You can also use a comparison expression anywhere that a **Boolean** value is needed such as in an <code> **If** , **While** , **Loop** , **ElseIf** </code> command or when assigning to or passing avalue to a boolean variable. In the following example, the value returned by the comparison expression is assigned to a **Boolean** variable: 

```
DclFld x *As (*Boolean)
x = 55 &lt; 30   // x is assigned False.
```

### See Also
[Boolean Expressions](aerConBooleanExpressions.html)
[Operators](aerConOperators.html)
[Comparison Operators](aerConComparisonOperators.html)
[Expressions](aerConExpressions.html) 
