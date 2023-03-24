---
title: Inheritance (Extensibility) Basics

Id: aerTourInheritanceBasics
TocParent: aerTourInheritanceMain
TocOrder: 5


---

The **<code>Extends</code>** keyword is used to declare a new class, called a *derived class* , based on an existing class, known as a *base class* . Derived classes inherit, and can extend, the properties, methods, events, fields, and constants defined in the base class. The following section describes some of the rules for inheritance, and the modifiers you can use to change the way classes inherit or are inherited: 

- All classes are inheritable by default unless marked with the **<code>NotExtensible</code>** 
                keyword. Classes can inherit from other classes in your project or from classes
                in other assemblies that your project references.
- Unlike languages that permit multiple inheritance, Encore RPG .NET permits
                only single inheritance in classes; that is, derived classes can have only one
                base class. Although multiple inheritance is not allowed in classes, classes *can* 
                implement multiple interfaces, which can effectively accomplish the same ends.
- To prevent exposing restricted items in a base class, the access type of a
                derived class must be equal to or more restrictive than its base class. For
                example, a * **<code>Public</code>**  class cannot inherit an * **<code>Internal</code>**  or a * **<code>Private</code>** 
                class, and an **<code>Internal</code>**  class cannot inherit a * **<code>Private</code>** 
                class.

### Extensible Modifiers
Encore RPG .NET introduces the following class-level options for the **<code>Modifier</code>** keyword for [BEGCLASS](BEGCLASS.html) to support inheritance: 

- * **<code>EXTENSIBLE</code>**   - specifies that all properties and
                methods for the class are extendable.
- * **<code>NOTEXTENSIBLE</code>** 
                - specifies that a property or procedure cannot be extended in a derived class.
- * **<code>MUSTEXTEND</code>**  -  specifies that a property or
                procedure in a base class specifies that all properties, methods and events for
                the base class must be extended in a derived class before it can be
                used.

### Overriding Properties and Methods in Derived Classes
By default, a derived class inherits methods from its base class. If an inherited property or method needs to behave differently in the derived class it can be *overridden* ; that is, you can define a new implementation of the method in the derived class. The following options of the **<code>Modifier</code>** keyword for [BEGFUNC](BEGFUNC.html), [BEGPROP](BEGPROP.html), [BEGSR](BEGSR.html) and [DCLEVENT](DCLEVENT.html) are used to control how properties and methods are overridden: 

- * **<code>OVERRIDABLE</code>** 
                - specifies that a property or method can be overridden in a derived
                class.
- * **<code>OVERRIDES</code>**  -  specifies that a property or method
                overrides a member inherited from a base class **.**
- * **<code>NOTOVERRIDABLE</code>** - specifies that a property or procedure cannot be overridden in a derived class.
- * **MUSTOVERRIDE**  -  specifies that a property or
                procedure in a base class must be overridden in a derived class before it can
                be used.

### See Also
[BEGCLASS](BEGCLASS.html)
[BEGFUNC](BEGFUNC.html)
[BEGPROP](BEGPROP.html)
[BEGSR](BEGSR.html)
[DCLEVENT](DCLEVENT.html)
[Inheritance and the .NET Framework](aerTourInheritanceandtheNETFramework.html) 
