---
title: Relation of Objects to Each Other

Id: aerConRelationofObjects
TocParent: aerConObjects
TocOrder: 1


---

Objects can be related to each other in several ways. One such relationship is hierarchical. Classes that are derived from more fundamental classes are said to have a hierarchical relationship. Class hierarchies are useful when describing items that are a subtype of a more general class. Derived classes inherit members from the class they are based on, allowing you to add complexity as you progress in a class hierarchy. 

Another way that objects are related is the object/object-container relationship. Container objects encapsulate other objects. For example, an instance of a class with a property that stores an object is a container object. 

One type of object containment is represented by collections. Collections are like arrays of objects that can be enumerated. Encore RPG supports a specific syntax in the form of ```If..Else..EndIf``` syntax blocks that allow you to iterate the items of a collection. Additionally, collections often allow you to use a method named ```Item``` property to retrieve elements by their index or by associating them with a unique string. Collections are easier to use than arrays because they allow you to add or remove items without using indexes. Because of their ease of use, collections are often used to store forms and controls. 

### See Also
[The Basics of Working with Objects](aerConBasicsofObjects.html)

[What is an Object?](aerConWhatisanObject.html) 
