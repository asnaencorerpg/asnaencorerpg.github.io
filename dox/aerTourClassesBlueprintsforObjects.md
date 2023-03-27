---
title: Classes

Id: aerTourClassesBluePrintsforObjects
TocParent: aerTourUnderstandingClassesMain
TocOrder: 5


---

Classes are a symbolic representation of an object. That is, they describe the properties, fields, methods, and events that make up objects. A single class can be used to create as many objects as necessary, and classes control user access to object items through encapsulation. 

### Classes and Objects
The terms "class" and "object" are sometimes used interchangeably, but in fact, classes describe the *structure* of objects, while objects are usable *instances* of classes. Each instance is an exact yet distinct copy of its class. Because an object is an "instance" of a class, the act of creating an object is called *instantiation* . 

For the most part, changing the data in one object does not change the data in any other object. The exception is *shared members,* class members declared with the ``` **Shared** (*Yes)``` keyword, which exist independently of specific instances of a class. 

### Encapsulation
*Encapsulation* is the ability to contain and control the access to a group of associated items. Classes provide one of the most common ways to encapsulate items. Without encapsulation, you would need to declare separate procedures and variables to store and manage information, and it would be difficult to work with more than one bank account at a time. Encapsulation lets you use the data and procedures in the class as a unit. You can work with multiple classes at the same time without confusion because each class is represented by a unique instance of the class. 

Encapsulation also allows you to control how the data and procedures are used. You can use access modifiers, such as ```Modifier** ( ***Private``` or ```*Protected)```, to prevent outside procedures from executing class methods or reading and modifying data in properties and fields. You should declare internal details of a class as ```*Private``` to prevent them from being used outside your class. 

### Inheritance
Like Encore RPG .NET structures, classes let you define data types that encapsulate a group of related items. Unlike structures, however, Visual RPG .NET classes can inherit and **extend** the characteristics of other classes. Classes that serve as a basis for new classes are called ***base** classes* . Classes derived from base classes are called *derived classes* . Derived classes inherit all the fields, properties, methods, and events defined in the base class. This means you can develop and debug a class once, and then reuse it as the basis for other classes. 

### Shared Members
By default, class data is specific to each instance of the class, but there may be occasions when you want a single data item to be shared among all objects created from a class. In such cases, you can use the **Shared** keyword to cause a variable to share the same value in all instances of a class. (Shared members are sometimes referred to as "static members" in other programming languages.) You can call shared methods directly using a class name without first creating an instance of the class. 

For more information about shared members, see [Shared Members](aerTourSharedMembers.html). 

### See Also
[Creating and Using Objects](aerTourCreatingandUsingObjectsMain.html)

[Inheritance](aerTourInheritanceMain.html)

[Inheritance Basics](aerTourInheritanceBasics.html)

[Shared Members](aerTourSharedMembers.html) 
