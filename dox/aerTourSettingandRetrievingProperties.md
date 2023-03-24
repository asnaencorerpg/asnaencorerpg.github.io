---
title: Setting and Retrieving Properties

Id: aerTourSettingandRetrievingProperties
TocParent: aerTourCreatingandUsingObjectsMain
TocOrder: 5


---

You can set their properties for forms and controls programmatically at run-time, or in design mode using the **Properties** window. The properties of most other objects, such as those from assemblies or objects you create, can only be set programmatically. 

Properties are divided into 3 categories:

1. Properties you can set and read are called *read-write* properties. 

2. Properties you can read but not modify are called *read-only* properties. 

3. Properties you can write but not read are called *write-only* properties.

You **get** the value of a property when you want to **find** the state of an object before your code performs additional actions, such as assigning the value to another object. For example, you can return the **```Text```** property of a text box control to determine the contents of the text box before running specific code. 

You **set** the value of a property when you want to **change** the appearance or behavior of an object. For example, you change the **```Visible```** property of a text box control to control whether the text box will display or not. 

**To Get property values** 

- Use the following syntax:
                
```
variable = object.property
```

**To Set property values** 

- Use the following syntax:
                
```
object.property = expression
```

The following statements provide examples of how to set properties:

```
TextBox1.Top = 500             //Sets the Top property to 500 twips.
TextBox1.Text = "Hello World"  //Displays *"Hello World* " in the text box.
```

### See Also
[Basics of Working with Objects](aerConBasicsofObjects.html)
[Creating and Using Objects](aerTourCreatingandUsingObjectsMain.html) 
