---
title: When to Use Interfaces

Id: aerTourWhentouseInterfaces
TocParent: aerTourInheritanceMain
TocOrder: 11


---

Interfaces allow you to separate the definition of objects from their implementation, allowing your objects to evolve without risk of breaking existing applications. This is extremely powerful. Both interfaces and class inheritance each have advantages and disadvantages, and you may end up using a combination of both in your projects. This topic and [When to Use Inheritance](aerTourWhentoUseInheritance.html) will help you determine which approach is best for your situation. 

### Safe Changes to Code
Interfaces eliminate a significant problem of class inheritance: the likelihood of breaking code when you make changes to your design. Even though class inheritance allows your classes to inherit implementation from a base class, it also forces you to make most of your design decisions when the class is first published. If your original assumptions turn out to be incorrect, you cannot always change your code safely in later versions. 

For instance, suppose you need to change the argument type of a method of a base class. You cannot safely change the original class, because applications designed for classes derived from the original may not compile correctly. This problem can be magnified because a single base class can affect hundreds of subclasses. 

A solution is to define a new method that overloads the original and takes a different Type. However, this might not be satisfactory because a derived class may need to override the method that takes the new type, and may not function properly if the method that takes the original type is not overridden also. Interfaces solve this problem by allowing you to publish an updated interface that accepts the new data type. 

### Flexibility in Implementation
There are several other reasons why you might want to use interfaces instead of class inheritance: 

- Interfaces are useful in cases where you cannot use class inheritance. For
                example, structures cannot inherit from classes, but they can implement
                interfaces.
- Interfaces are better in situations in which you do not need to inherit
                implementation from a base class. Interfaces are better suited to situations in
                which your applications require many possibly unrelated object types to provide
                certain functionality.
- Interfaces are more flexible than base classes because you can define a single
                implementation that can implement multiple interfaces.

### See Also
[When to Use Inheritance](aerTourWhentoUseInheritance.html) 
