---
title: Object Variable Declaration

Id: aerConObjectVariableDeclaration
TocParent: aerConObjectVariables
TocOrder: 10


---

You use a normal declaration statement to declare an object variable, but for the data type, you specify either <code> **Object** </code> or the *object class* . The object class is the specific class from which the object is to be instantiated. When you declare a variable with a specific object class, it can access all the methods and properties exposed by that class. If you declare the variable with **Object** , it can use only the members of the <code> **Object** </code> class. 

Use the following syntax to declare an object variable:

```
DCLFLD *variablename*   *New { *objectclass*  | Object}
```

You can also use <code>* **Protected** </code>, <code>* **Internal** </code>, <code>* **Private** </code>, <code>* **Public** </code> for the declaration. 

Sometimes the object class is not known until the procedure runs. In this case, you must declare the object variable with the <code> ***Object** </code> data type. 

Declaring an object variable as a specific object class gives you several advantages: 

- Automatic type checking.
- Improved readability.
- Fewer errors in your code.
- Faster code execution.

### Flexibility of Object Variables
When working with objects in an inheritance hierarchy, you have a choice of which class to use for declaring your object variables. In making this choice, you must balance flexibility of object assignment against access to a class's members. 

### See Also
[Object Variable Assignment](aerConObjectVariableAssignment.html) 
