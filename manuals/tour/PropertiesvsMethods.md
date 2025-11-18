---
title: Properties vs. Methods

Id: aerTourPropertiesvsMethods
TocParent: aerTourClassPropertiesFieldsandMethodsMain
TocOrder: 20


---

Properties and methods are similar in that both are implemented as routines that accept arguments. In general, properties **store data** for an object, and methods are **actions** an object can be asked to perform. 

Some object characteristics are obviously properties, such as `Name`, and some are obviously methods, such as `Add` and `Delete`. In other cases, it is not obvious which class members should be properties and which should be methods. For example, the `Item` method of a collection class stores and retrieves data and can be implemented as an indexed property. On the other hand, it is also reasonable to implement `Item` as a method. 

### Property Syntax vs. Method Syntax
One way to decide how to implement a class member is to consider how you want it to be used. Although the syntax for retrieving information from a parameterized property is almost identical to the syntax used with a method implemented as a function, the syntax for modifying such a value is slightly different. For example, if you implement the member of a class as a property, the following syntax describes how it would be used: 

```
MyObject.MyProperty(Index) = NewValue
```

If you implement the class member as a method, the value being modified must be an argument. The following code fragment describes equivalent syntax usage: 

```
MyObject.MyProperty(Index,NewValue)
```

### Error Messages
Another factor to consider when choosing how to implement a class member is what kind of messages will be generated when your class is used incorrectly. If someone accidentally attempts to assign a value to a read-only property, a different error message is returned than in response to a similar call to a method. Class members that are implemented correctly return error messages that are easier to interpret. 

### See Also
[Adding Fields and Properties to a Class](AddingFieldsandPropertiestoaClass.html) 
