---
title: Treating Forms as Objects

Id: aerTourTreatingFormsasObjects
TocParent: aerTourCreatingandUsingObjectsMain
TocOrder: 15


---

Forms are graphical objects that make up your applications user interface. Within Encore RPG, classes define how forms are displayed and what they can do. When a form is displayed at runtime, Encore RPG .NET creates an instance of the **<code>Form</code>** class that you can use like any other object. You can add custom methods and properties to forms and access them from other forms or classes in your application. 

**To create a new method for a form** 

- Add a procedure declared as <code> **Public** </code>, as in the following code:
                
```
BegProp MyProp Access (*Public)
  ...//Add code for your method
EndProp
```

**To add a new field to a form** 

- Declare a public variable in the form module, as in the following code:
                
```
DclFld MyField Type (*Integer) Len (2)
```

**To access methods on a different form** 

1. Create a new instance of the form whose methods you want to access. When you
                reference a form name, you are actually referencing the class the form belongs
                to, not the object itself.
2. Assign the form to an object variable. The object variable references a new
                instance of the form class.

It is not necessary to show a form object to use its methods. To display the new form, you need to add the following code: 

```
SHOW.newForm1
```

### See Also
[Property Procedures](aerTourPropertiesandPropertyProcedures.html) 
