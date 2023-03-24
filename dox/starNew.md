---
title: "*New"

Id: starNew
TocParent: aerLrfSpecialValuesMain
TocOrder: 1


---

The * **New** special value introduces a **New** clause, which creates a new object instance. * **New** must specify a defined class from which the instance can be created. You can use * **New** in a declaration statement or an assignment statement. When the statement is executed, it calls the constructor of the specified class, passing any arguments you have supplied: 

```
DclFld Obj Type( *Object )
Obj = *New SomeClass("String required by constructor")
// ...
DclFld MyLabel Type ( Label ) New()
```
Since arrays are classes, **New** can create a new array instance:

```
DclArray MyArray Type( *Integer4 ) Rank( 1 )
MyArray = *New *Integer4[] {0, 1, 2, 3}
```
The common language runtime throws an **OutOfMemoryException** error if there is insufficient memory to create the new instance. 

The * **New** keyword is used in this context: DclFld Op Code 

### See Also
<a href="aerConUsingConstructors">Using Constructors</a> 
