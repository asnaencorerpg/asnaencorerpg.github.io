---
title: Object Variable Values

Id: aerConObjectVariableValues
TocParent: aerConObjectVariables
TocOrder: 15


---

An object variable can refer to data of any type. The value you store in an object variable is kept elsewhere in memory, while the variable itself holds a pointer to the data. 

You can use the <code>* **TypeOf** </code> operator to determine whether an object variable currently refers to a specific data type. The <code>* **TypeOf** </code> and <code> ***Is** </code> operators evaluate to <code> **True** </code> if the run-time type of the operand is derived from or implements the specified type. 

You can declare and use an array of <code> **Object** </code> variables. This is useful when you need to handle a variety of data types and object classes. All the elements in an array must have the same declared data type. Declaring this data type as <code> **Object** </code> allows you to store objects and class instances alongside other data types in the array. 

### See Also
[<code>*Is</code> Operator](Is_Operator.html)
[<code>*TypeOf</code> Operator](Typeof_Operator.html) 
