---
title: Operators

Id: aerConOperators
TocParent: aerConLanguageConceptsMain
TocOrder: 20


---

An operator performs an operation on one or more value-returning code elements. This can mean an arithmetic operation such as addition or multiplication; a concatenation operation that combines two strings into a new string; a comparison operation that determines which of two values is greater; a logical operation evaluating whether two expressions are both true. Operators combined with value-returning code elements such as literals or variables form [expressions](aerConExpressions.html). 

The following is an example of a statement that uses the simple assignment operator (```=```): 

```
x = 85
```

In the preceding example, the assignment operator performs the assignment operation: it takes the value on the right side of the operator and assigns it to the variable on the left. Several operators can perform actions in a single expression or statement, as demonstrated below: 

```
x = 85 + y * z ^ 2
```

In this example, the operations in the expression on the right side of the assignment operator are performed, and the resulting value is assigned to the variable <code class="ce">x```, on the left. There is no limit to the number of operators that can be combined into an expression, but an understanding of **Operator Precedence** is necessary to ensure that you get the results you expect. 

### In This Section

[Arithmetic Operators](aerConArithmeticOperators.html)

Discusses operators used to perform many familiar arithmetic operations that
                involve calculation of numeric values represented by literals, variables, other
                expressions, function and property calls, and constants.


[Comparison Operators](aerConComparisonOperators.html)

Discusses operators that compare two expressions and return a **Boolean**  value 	representing the result of the comparison.


[Concatenation Operators](aerConConcatenationOperators.html)

Provides information on the **+**  and **&**  operators, which join 			multiple strings into
                a single string.


[Logical 					Operators](aerConLogicalOperators.html)

Provides information on operators that compare **Boolean** 
                expressions and return a **Boolean**  result.


### Related Sections

[Expressions](aerConExpressions.html)

Shows how to combine elements with operators to yield new values.


[Operators](aerLrfOperatorsMain.html)

Provides links to Language Reference topics covering all Encore RPG operators, 	listed by category.


### See Also
[Language Concepts](aerConLanguageConceptsMain.html) 
