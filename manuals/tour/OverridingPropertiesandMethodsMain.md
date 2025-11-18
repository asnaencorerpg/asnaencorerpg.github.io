---
title: Overriding Properties and Methods

Id: aerTourOverridingPropertiesandMethodsMain
TocParent: aerTourClassPropertiesFieldsandMethodsMain
TocOrder: 30


---

Derived classes inherit properties and methods defined in their base class. This is helpful because it means you can reuse these items when appropriate for the class you are using. If the inherited, or extended member cannot be used "as is", you have the option of using the `Modifier` keyword to define a new implementation, provided that the property or method in the base class is marked with the `Modifier` keyword. 

The following rules apply to overriding methods. 

- You can only override members that are marked with the `Modifier(*Overridable)` keyword in their base class.
- Properties and methods are not overridable by default.
- Overridden members must have the same arguments as the inherited members from
                the base class.

### See Also
[Overloaded Properties and Methods](OverloadedProperties.html)

[Override Modifiers](OverrideModifiers.html) 
