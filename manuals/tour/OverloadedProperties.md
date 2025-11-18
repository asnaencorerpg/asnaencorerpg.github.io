---
title: Overloaded Properties

Id: aerTourOverloadedProperties
TocParent: aerTourClassPropertiesFieldsandMethodsMain
TocOrder: 25


---

Overloading is the creation of more than one procedure, instance constructor, or property in a class with the same name but different argument types. 

Overloading is especially useful when your object model dictates that you employ identical names for procedures that operate on different data types. 

Overloading makes it easier to use properties or methods because it provides a choice of data types that can be used. 

### Overloading Rules

You create an overloaded member for a class by adding two or more properties or methods with the same name. Except for overloaded derived members,each overloaded member must have different parameter lists, and the following items cannot be used as a differentiating feature when overloading a property or procedure: 

- Special value `*ByRef`, that applies to a member, or parameters
                of the member.
- Names of parameters.
- Return types of procedures.

### See Also
[*ByRef](StarByRef.html)

[Overriding Properties and Methods](OverridingPropertiesandMethodsMain.html) 
