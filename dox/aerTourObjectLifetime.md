---
title: Object Lifetime

Id: aerTourObjectLifetime
TocParent: aerTourUnderstandingClassesMain
TocOrder: 15


---

Objects begin life when an instance of a class is created using the **<code>New</code>** keyword. New objects often require initialization tasks to be performed before they are used for the first time. Common initialization tasks include opening files, connecting to a database, and reading the values of registry keys. 

Objects end life after they leave scope and are released by the common language runtime (CLR). 

### Initializing Objects
The [BEGCONSTRUCTOR](BEGCONSTRUCTOR.html) and [ENDCONSTRUCTOR](ENDCONSTRUCTOR.html) operation codes in Encore RPG initialize objects. **<code>BEGCONSTRUCTOR</code>** can run only once when a class is created, and it cannot be called explicitly anywhere other than in the first line of code in another constructor from either the same class or from a derived class. Furthermore, the code in the method always runs before any other code in a class. Encore RPG .NET implicitly creates a **New** constructor at run-time if you do not explicitly define a **New** procedure for a class. 

### See Also
[BEGCONSTRUCTOR](BEGCONSTRUCTOR.html)
[ENDCONSTRUCTOR](ENDCONSTRUCTOR.html)
[Using Constructors](aerTourUsingConstructors.html) 
