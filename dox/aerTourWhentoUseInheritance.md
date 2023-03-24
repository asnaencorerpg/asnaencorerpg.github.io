---
title: When to Use Inheritance

Id: aerTourWhentoUseInheritance
TocParent: aerTourInheritanceMain
TocOrder: 10


---

Inheritance is a useful programming concept, but it is easy to use inappropriately, as interfaces often do the job better. Refer to this topic and [When to Use Interfaces](aerTourWhentouseInterfaces.html) to help you understand when each should be used. 

Inheritance is a good choice when: 

- Your inheritance hierarchy represents an *is-a*  relationship and not a *has-a* 
                relationship.
- You can reuse code from the base classes.
- You need to apply the same class and methods to different data types.
- You want to make global changes to derived classes by changing a base class.

These considerations are discussed in order below.

### Inheritance and "Is a" Relationships
Two ways to show class relationships in object-oriented programming are "is a" and "has a" relationships. In an "is a" relationship, the derived class is clearly a kind of the base class. 

Objects in an inheritance hierarchy should have an "is a" relationship with their base class because they inherit the fields, properties, methods, and events defined in the base class. Classes that represent a "has a" relationship with other classes are not suited to inheritance hierarchies because they may inherit inappropriate properties and methods. 

### Reuse Code From Base Classes
Another reason to use inheritance is the advantage of code reuse. Well-designed classes can be debugged once and used over and over as a basis for new classes. 

Although inheritance-based code reuse is a powerful tool, it also has associated risks. Even the best-designed systems sometimes change in ways the designers could not foresee. Changes to an existing class hierarchy can sometimes have unintended consequences. 

### Interchangeable Derived Classes
Derived classes in a class hierarchy can sometimes be used interchangeably with their base class, a process called inheritance-based polymorphism. This approach combines the best features of interface-based polymorphism with the option of reusing or overriding code from a base class. 

This approach poses some problems. If someone decides to add an ellipse option later, it will be necessary to alter the source code; it is possible that your target users will not even have access to your source code. A more subtle problem is that drawing an ellipse requires another parameter (ellipses have both a major and a minor diameter) that would be irrelevant to the line case. If someone then wants to add a polyline (multiple connected lines), then another parameter would be added, and it would be irrelevant to the other cases. 

Inheritance solves most of these problems. Well-designed base classes leave the implementation of specific methods up to the derived classes, so that any kind of shape can be accommodated. Other developers can implement methods in derived classes by using the documentation for the base class. Other class items (such as the x- and y-coordinates) can be built into the base class because all descendants use them. For example, <code class="ce">Draw``` could be a ``` **MustOverride** ``` method: 

This approach is useful because other developers, who do not have access to your source code, can extend your base class with new derived classes as needed. 

At this point it might be good to reevaluate if the derived class truly represents an "is a" relationship, or have we inadvertently used a "has a" relationship. If the new rectangle class is just composed of lines, then inheritance is not the best choice. However, if the new rectangle is a line with a width property, then the "is a" relationship is maintained. 

### Global Changes to Derived Classes Through the Base Class
One of the most powerful features of inheritance is the ability to make changes in a base class that propagate to derived classes. When used carefully, you can update the implementation of a single method, and dozens, or even hundreds of derived classes can use the new code. However, this can be a dangerous practice because such changes may cause problems with inherited classes designed by other people. Care must be taken to ensure that the new base class is compatible with classes that use the original. You should specifically avoid changing the name or type of base class members. 

The safest way to change a base class is to simply add new members. For example, you could add a new field to store the additional 4 digits in the zip code example discussed previously. That way, client applications can be updated to use the new field without breaking existing applications. The ability to extend base classes in an inheritance hierarchy is an important benefit that does not exist with interfaces. 

### See Also
[When to Use Interfaces](aerTourWhentouseInterfaces.html) 
