---
title: Setting and Retrieving Properties

Id: aerConSettingandRetrievingProperties
TocParent: aerConProperties
TocOrder: 10


---

When working with forms and controls, you can set their properties programmatically at run-time, or you can set them in design mode using the **Properties** window. The properties of most other objects, such as objects from assemblies or objects you create, can only be set programmatically. 

Properties you can set and read are called *read-write* properties. Properties you can read but not modify are called *read-only* properties. Properties you can write but not read are called *write-only* properties. 

You set the value of a property when you want to change the appearance or behavior of an object. For example, you change the **Text** property of a text box control to modify the contents of the text box. 

You get the value of a property when you want to find the state of an object before your code performs additional actions, such as assigning the value to another object. For example, you can return the <code> **Text** </code> property of a text box control to determine the contents of the text box before running code that might change the value. 

### See Also
[The Basics of Working with Objects](aerConObjects.html) 
