---
title: Object Variable Assignment

Id: aerConObjectVariableAssignment
TocParent: aerConObjectVariables
TocOrder: 5


---

        You use a normal assignment statement to assign an object to an object
        variable. You can assign an object expression or the <code>* **Nothing** </code> figurative
        constant.

<code> ***Nothing** </code> means there is no object currently assigned to the variable. When your code begins running, your object variables are initialized to <code> ***Nothing** </code>, except for those whose declarations include assignment. 

You can combine assignment with declaration by using the <code>* **New** </code> operator. 

Setting an object variable to <code>* **Nothing** </code> discontinues the association of the variable with any specific object. This prevents you from accidentally changing the object by changing the variable. It also allows you to test whether the object variable points to a valid object. 

### Current Instance of an Object
The *current instance* of an object is the one in which the code is currently executing. Since all code executes inside a procedure, the current instance is the one in which the procedure was invoked. 

The <code>* **This** </code> figurative constant acts as an object variable referring to the current instance. If a procedure is not shared, it can use the <code>* **This** </code> constant to obtain a pointer to the current instance. Shared procedures cannot be associated with a single instance of an object. 

Using <code> ***This** </code> is particularly useful for passing the current instance to a procedure in another module. 

### See Also
[Object Variables](aerConObjectVariables.html)
[Object Variable Declaration](aerConObjectVariableDeclaration.html) 
