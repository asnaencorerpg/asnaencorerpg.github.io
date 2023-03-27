---
title: The Basics of Working with Objects

Id: aerConBasicsofObjects
TocParent: aerConObjects
TocOrder: 2


---

Almost everything you do in Encore RPG involves objects. This topic shows you some ways that the elements of objects are used. 

### Member Access
You access the members of an object by specifying, in order, the name of the object, a period, and the name of the member you want to use. For example, if you have an object named ```Obj1``` that has a property named ```Prop1``` you could use the syntax <code class="ce">Obj1.Prop1``` to access that property. In some cases you need to use several dots because objects can contain other objects. For example, you could use the syntax <code class="ce">Obj1.Prop1.X``` if the property ```Prop1``` is an object that contains a field named ```X```. 

### Fields and Properties
Properties and fields represent information stored in an object. The values of fields and properties are retrieved and set with assignment statements the same way that variables are retrieved and set. The following example sets and retrieves the value of a field and a property. 

```
DclFld X Type (*Integer) Len (4)<br />  x = 8 DclFld
  TheOtherForm Type( Form2 ) New( *Dft ) // Declares an instance of a class.
```

### Methods
Methods are procedures defined within a class. Methods are used like subroutines or functions, but are accessed by way of the object to which they belong. The following code fragment calls a function and a subroutine declared in an object: 

```
DclFld TheOtherForm Type( Form2 ) New( *Dft )   // Declares an instance of a class
  DclFld Y Type (*Integer)
  // Retrieves a value from a method declared as a function.
  Y = Obj2.GetNumber   
  Obj2.StoreNumber(Y)   // Calls a method declared as a subroutine.
```

### See Also
[What Is an Object?](ecrConWhatisanObject.html)

[Relationship of Objects](ecrConRelationofObjects.html) 
