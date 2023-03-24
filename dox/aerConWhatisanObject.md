---
title: What is an Object?

Id: aerConWhatisanObject
TocParent: aerConObjects
TocOrder: 0


---

An object is a combination of code and data that can be treated as a unit. An object can be a piece of an application, like a control or a form. An entire application can also be an object. 

Objects let you declare variables and procedures once and then reuse them whenever needed. For example, if you want to add a spell checker to an application you could define all the variables and support functions to provide spelling check functionality to your application. However, if you create your spell checker as a class, you can reuse it in other applications by adding a reference to the compiled assembly. Better yet, you may be able to save yourself some work by using a spell checker class that someone else has already developed. 

Each object in Encore RPG is defined by a class. Classes describe the fields, properties, methods, and events of an object. Objects are instances of classes; you can create as many objects as you need once you have created a class. 

To understand the relationship between an object and its class, think of cookie cutters and cookies. The cookie cutter is the class. It defines the characteristics of each cookie — for instance, size and shape. The class is used to create objects. The objects are the cookies. 

Two examples of the relationship between classes and objects in Encore RPG may make this clearer: 

- The controls on the Toolbox in Encore RPG represent classes. When you drag and
                drop a control from the toolbox onto a form, you are actually creating an
                object — an instance of a class.
- The form you work with at design-time is a class. At run-time, Encore RPG
                creates an instance of the form's class.

Objects are created as identical copies of their class. Once they exist as individual objects, however, their properties can be changed. For example, if you add three check boxes to a form, each check box button object is an instance of the <code> **CheckBox** </code> class. The individual <code> **CheckBox** </code> objects share a common set of characteristics and capabilities (properties, fields, methods, and events), defined by the class. However, each has its own name, can be separately enabled and disabled, can be placed in a different location on the form. 

### See Also
[The Basics of Working with Objects](aerConBasicsofObjects.html)
[Relation of Objects to Each Other](aerConRelationofObjects.html) 
