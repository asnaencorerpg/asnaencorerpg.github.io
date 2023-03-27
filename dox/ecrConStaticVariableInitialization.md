---
title: Static Variable Initialization

Id: aerConStaticVariableInitialization
TocParent: aerConDeclaredElementsLifetime
TocOrder: 0


---

You can initialize the value of a static local variable as part of its declaration. If you declare an array to be **Static** , you can initialize its **Rank** (number of dimensions), the length of each dimension, and the values of the individual elements. 

You can declare static variables with the same name in more than one procedure. If you do this, the Encore RPG compiler considers each such variable to be a separate element. The initialization of one of these variables does not affect the values of the others. The same applies if you define a procedure with a set of overloads and declare a static variable with the same name in each overload. 

You can declare a static local variable in a class, that is, inside a procedure in that class. However, you cannot declare a static local variable in a structure. 

### See Also
[Accessibility](ecrConAccessibility.html)

[Declared Elements](ecrConDeclaredElements.html)

[DCLFLD](DCLFLD.html)

[Lifetime](ecrConDeclaredElementsLifetime.html)

[Accessibility](ecrConAccessibility.html)

[Variables](Variables.html)

[Variable Declaration](ecrConVariableDeclaration.html) 
