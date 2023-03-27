---
title: Introduction to Objects in Encore RPG

Id: aerTourIntroductiontoObjects
TocParent: aerTourCreatingandUsingObjectsMain
TocOrder: 0


---

Almost everything you do in Encore RPG is associated with objects. If you are new to object-oriented programming, the following terms and concepts will help you get started. 

### Classes and Objects
The words "class" and "object" are used so much in object-oriented programming that it is easy to get the terms mixed up. Generally speaking, a *class* is an abstract representation of something, whereas an *object* is a usable example of the thing the class represents. The one exception to this rule is shared class members, which are usable in both instances of a class and object variables declared as the type of the class. 

### Fields, Properties, Methods, and Events
Classes are made of fields, properties, methods, and events. Fields and properties represent information that an object contains. Fields are like variables in that they can be read or set directly. For example, if you have an object named Car you could store its color in a field named Color. 

Properties are retrieved and set like fields, but are implemented using **```BEGGET``` and ``` **BEGSET``` commands, which provide more control on how values are set or returned. The layer of indirection between the value being stored and the procedures that use this value helps isolate your data and allows you to validate values before they are assigned or retrieved. 

Methods represent actions that an object can perform. For example, a ```Vehicle``` object could have ```Type, Drive```, and ```Stop``` methods. You define methods by adding procedures, either **```BEGSR``` or ```BEGFUNC```** routines or functions, to your class. 

Events are notifications an object receives from, or transmits to, other objects or applications. Events allow objects to perform actions whenever a specific occurrence takes place. An example of an event for the ```Vehicle``` class would be a ```Check_Engine``` event. Events can come from other objects, applications, or user input such as mouse clicks or key presses. 

### Encapsulation, Inheritance, and Polymorphism
True .NET object-orient programming also requires objects to support three qualities: encapsulation, inheritance, and polymorphism. 

*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object. Objects can control how properties are changed and methods are executed. For example, an object can validate values before allowing property changes. Encapsulation also makes it easier to change your implementation at a latter date by letting you hide implementation details of your objects, a practice called *data hiding* . 

*Inheritance* describes the ability to create new classes based on an existing class. The new class inherits all the properties and methods and events of the base class, and can be customized with additional properties and methods. For example, you can create a new class named ```Car``` based on the ```Vehicle``` class. The ```Car``` class inherits the ```Color``` property from the ```Vehicle``` class and can have additional properties such as ```FourWheelDrive```. 

*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways. Polymorphism is essential to object-oriented programming because it allows you to use items with the same names, no matter what type of object is in use at the moment. For example, given a base class of ```Vehicle```, polymorphism enables the programmer to define different ```StartEngine``` methods for any number of derived classes. The ```StartEngine``` method of a derived class named ```DieselCar``` may be completely different from the method with the same name in the base class. 

### Overloading and Overriding
Overloading and overriding are similar concepts that can be easy to confuse. Although they allow you to create members with the same name, there are some important differences. 

- Overloaded members are used to provide different versions of a property or
                method that have the same name, but that accept different numbers of parameters,
                or parameters with different data types.
- Overridden properties and methods are used to introduce to objects an inherited
                property or method that is not appropriate in a derived class. Overridden
                members must accept the same data type and number of arguments. Derived classes
                inherit overridden members.

### See Also
[Objects](ecrConObjects.html)

[Creating and Using Objects](ecrTourCreatingandUsingObjectsMain.html)

[Inheritance](ecrTourInheritanceMain.html)

[Overloaded Properties and Methods](ecrTourOverloadedProperties.html)

[Overriding Properties and Methods](ecrTourOverridingPropertiesandMethodsMain.html) 
