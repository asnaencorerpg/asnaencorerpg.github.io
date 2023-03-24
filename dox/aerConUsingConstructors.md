---
title: Using Constructors

Id: aerConUsingConstructors
TocParent: aerConObjects
TocOrder: 4


---

Constructors control the creation of objects.

To create a constructor for a class, create a procedure named [BEGCONSTRUCTOR](BEGCONSTRUCTOR.html) anywhere in the class definition. To create a parameterized constructor, specify the names and data types of arguments to ```DclFld *New``` just as you would specify arguments for any other procedure. 

When you define a class derived from another class, the first line of a constructor must be a call to the constructor of the base class, unless the base class has an accessible constructor that takes no parameters. Use [ENDCONSTRUCTOR](ENDCONSTRUCTOR.html)  to destroy and release resources. 

### See Also
[BEGCONSTRUCTOR](BEGCONSTRUCTOR.html)
[ENDCONSTRUCTOR](ENDCONSTRUCTOR.html)  
