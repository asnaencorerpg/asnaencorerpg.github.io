---
title: Objects, Properties, Methods, and Events

Id: aerConObjPropMethodsandEvents
TocParent: aerConObjects
TocOrder: 3


---

Objects, properties, methods, and events are the basic units of object-oriented programming. An object is an element of an application, representing an *instance* of a class. Properties, methods, and events are the building blocks of objects, and constitute their *members* . 

### Objects
An object represents an instance of a class such as an <code> **ArrayList** </code> or <code> **Queue** </code>. In Encore RPG code, you must *instantiate* an object before you can apply one of the object's methods or change the value of one of its properties. Instantiation is the process by which an instance of a class is created and assigned to an object variable. An example is shown below: 

```
DclFld MyList Type (Sytem.Collections.ArrayList) New (*Dft)
```

In this example, the variable <code>x</code> is assigned to refer to a new instance of the <code>ArrayList</code> class. 

### Properties
A property is an attribute of an object that defines one of the object's characteristics, such as size, value, location, or anaspect of its behavior, such as whether it is expandable or fixed size. To change the characteristics of an object, you change the values of its corresponding properties. 

To set the value of a property, affix the reference to an object with a period, the property name, an equal sign (=), and the new property value. For example, the following code changes the capacity of an ArrayList by setting the <code> **Capacity** </code> property: 

```
Begsr DoubleCapacity
   MyList.Capacity = MyList.Capacity * 2 
EndSr
```

Note that you can't set some properties. The Help topic for each property indicates whether you can set that property (read/write), only read the property (read-only), or only write the property (write-only). 

You can retrieve information about an object by returning the value of one of its properties. The following procedure writes to the console the current number of items in a list. 

```
BegSr ShowListSize() 
   System.Console.WriteLine("Number of Items in the list {0}", MyList.Count)            
EndSr
```

### Methods
A method is an action that an object can perform. For example, <code> **Add** </code> is a method of the <code>ArrayList</code> object, which as you can imagine, it adds an object at the end of the ArrayList. The ArrayList class belongs to a namespace called System.Collections, this namespace has other similar classes. 

The following example demonstrates the <code> **Add** </code> method of a <code>System.Collections.Queue</code> object: 

```
// Instantiates a timer object. 
    DclFld OrderQueue Type (System.Collections.Queue) New (*Dft)   
    // Add a couple of orders to the queue
    OrderQueue.Add("ORD1234")
    OrderQueue.Add("ORD5678")

```

### Events
An event is an action recognized by an object, such as clicking the mouse or pressing a key, and for which you can write code to respond. Events can occur as a result of a user action or program code, or they can be triggered by the system. You can also develop your own custom events to be raised by your objects and handled by other objects. 

### See Also
[Events](aerConEvents.html)
[Objects](aerConObjects.html)
[Setting and Retrieving Properties](aerConSettingandRetrievingProperties.html) 
