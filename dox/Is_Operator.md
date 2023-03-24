---
title: "*Is Operator"

Id: Is_Operator
TocParent: aerLrfOperatorsMain
TocOrder: 13


---

The ***Is** operator is used to check whether the run-time type of an object is compatible with a given type. The ***Is** operator is used in an expression of the form: 

```

 ** *expression*  *Is *type* ** 
        
```

### Parts

*expression* 

An expression of a reference type.


*type* 

A type.


### Example
An ***Is** expression evaluates to true if both of the following conditions are met: 

- *expression*  is not **null** .
- *expression* can be cast to *type* . That is, a cast expression of the form
                <code class="ce">(type)(expression)</code> will complete without throwing an exception.

A compile-time warning will be issued if the expression <code class="ce">expression is type</code> is known to always be **True** or always be **False** . 

The ***Is** operator cannot be overloaded. 

Note that the ***Is** operator only considers reference conversions. Other conversions, such as user-defined conversions, are not considered by the **is** operator. 

### See Also
[Operators and Their Precedence](Expression_Operators_and_their_Precedence.html) 
