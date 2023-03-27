---
title: Properties

Id: aerConProperties
TocParent: aerConLanguageConceptsMain
TocOrder: 21


---

A **property** routine is a series of Encore RPG statements that manipulate a custom property on a program, class, or structure. 

A property differs from a public variable or a field in the following respects: 

- You implement a property with executable code (```BEGPROP```),
                rather than with a single declaration statement.
- **Property** 
                procedures are executed when the property value is set or retrieved. This
                allows a class to perform custom actions when client code accesses the
                property.
- A property does not have any storage location associated with its declaration.
                Although its **Property** 
                procedures often define local variables and constants, these are usually not
                available to the code accessing the property. Therefore, while you can include
                a variable or a field as a member of a structure or array, you cannot do this
                with a property.
- You can define a property as read-only, write-only, or read/write. The default
                is read/write.

Encore RPG provides the following **Property** procedures: 

- ```BEGGET```
                operations return the value of a property; they are called when the property is
                accessed in an expression.
- ```BEGSET```
                operations set a property to a value, including an object
                reference; they are called when a value is assigned to the property.

You usually define **Property** procedures in pairs, using the ```BEGGET``` and ```BEGSET``` op codes, but you can define either procedure alone if the property is read-only (```BegGet```) or write-only (```BegSet``` ). 

### See Also
[BEGGET](BEGGET.html)

[BEGPROP](BEGPROP.html)

[BEGSET](BEGSET.html) 
