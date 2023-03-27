---
title: Declared Element Lifetime

Id: aerConDeclaredElementsLifetime
TocParent: aerConDeclaredElements
TocOrder: 1


---

The *lifetime* of a declared element is the period of time during which it is available for use. Variables are the only elements that have lifetimes; for this purpose, the compiler treats procedure arguments and function returns as special cases of variables. The lifetime of a variable represents the period of time during which it can hold a value. Its value can change over its lifetime, but it always holds some value. 

### Beginning of Lifetime
A local variable's lifetime begins when execution enters the procedure in which it is declared. Every local variable is initialized to the default value for its data type as soon as the procedure begins execution. Numeric variables (including * **Byte** and ***Char** ) are initialized to zero, * **Date** variables to midnight of January 1 of the year 1, **Boolean** variables to **False** , and reference type variables (including strings, arrays, and **Object** ) to * **Nothing** . 

Each member of a structure variable is initialized as if it were a separate variable. Similarly, each element of an array variable is initialized individually. 

If a variable is declared with an initializer, the specified value is assigned to the variable when its declaration statement is executed, as shown in the following example: 

```
DCLFLD Name( MyField ) Type( *Integer )
 MyField = 45   //MyField had previously been initialized to 0.
```

Variables declared within a block inside a procedure are initialized to their default values on entry to the procedure. These initializations take effect whether or not the block is ever executed. 

### End of Lifetime
When a procedure terminates, the values of its local variables are not preserved, and the memory used by the local elements is reclaimed. The next time the procedure is executed, all its local elements are created afresh and the local variables are initialized. 

When an instance of a class or structure terminates, its nonshared variables lose their values. Each new instance of the class or structure creates all its nonshared elements and initializes the nonshared variables. **Shared** elements are preserved until your application stops running. 

### Different Lifetimes
A variable declared at module level typically exists for the entire time your application is running. a nonshared variable declared in a class or structure exists as a separate copy for each instance of the class or structure in which it is declared; each such variable has the same lifetime as its instance. However, a **Shared** variable has only a single lifetime, which lasts for the entire time your application is running. 

Local variables or arrays declared with [DCLFLD](DCLFLD.html) or [DCLARRAY](DCLARRAY.html) exist only while the procedure in which they are declared is executing. This applies also to that procedure's arguments and to any function return. However, if that procedure calls other procedures, the local variables retain their values while the called procedures are running. 

### Extension of Lifetime
If a local variable or array is declared with the **Static(*Yes)** keyword, its lifetime is longer than the execution time of the procedure in which it is declared. If the procedure is inside a module, the static variable survives as long as your application continues running. 

If a static variable is declared in a procedure inside a class, the variable's lifetime depends on whether the procedure is shared. If the procedure is declared with the **Shared(*Yes)** keyword, the variable's lifetime continues until your application terminates. If the procedure is nonshared, its static variables are instance members of the class, and their lifetimes are the same as that of the class instance. 

### Related Sections

[Declared Element Characteristics](aerConDeclaredElementCharacteristics.html)

Covers the characteristics, such as data type, lifetime, scope and
                accessibility, of declared elements.


[Declared 	Element Scope](aerConDeclaredElementsScope.html)

Describes the scope of access of a declared element.


[Declared Element Accessibility](aerConAccessibility.html)

Describes the accessibility of a declared element.


### See Also
[DCLFLD](DCLFLD.html)

[DCLARRAY](DCLARRAY.html) 
