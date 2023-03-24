---
title: Using Constructors

Id: aerTourUsingConstructors
TocParent: aerTourUnderstandingClassesMain
TocOrder: 20


---

Constructors control the creation and destruction of objects. 

To create a constructor for a class, create a procedure named **```BegConstructor```** anywhere in the class definition. To create a parameterized constructor, specify the names and data types of arguments to **```BegConstructor```** just as you would specify arguments for any other procedure, as in the following code: 

```
 BegConstructor Access (*Public)
```

When you define a class derived from another class, the first line of a constructor must be a call to the constructor of the base class, unless the base class has an accessible constructor that takes no parameters. 

After writing code to call the parent object's constructor, you can add any additional initialization code to the **```BegConstructor```** procedure. **```BegConstructor```** can accept arguments when called as a parameterized constructor. These parameters are passed from the procedure calling the constructor. 

### See Also
[Object Lifetime: How Objects Are Created and Destroyed](aerTourObjectLifetime.html) 
