---
title: Declared Element Scope

Id: aerConDeclaredElementsScope
TocParent: aerConDeclaredElements
TocOrder: 2


---

The *scope* of a declared element is the set of all code that can refer to it without qualifying its name. An element can have *scope* at one of the following levels: 

- Block access — available only within the code block in which it is
                declared.
- Procedure access — available only within the procedure in which it is
                declared.
- Program  access — available to all code within the program, or class in
                which it is declared.
- Namespace access — available to all code in the namespace.

These levels of access progress from the narrowest (block) to the widest (namespace), where *narrowest scope* means the smallest set of code that can refer to the element without qualification. 

You specify the scope of an element when you declare it depending on the following factors: 

- The region (block, procedure, module, class, or structure) in which you declare
                the element.
- The namespace containing the element's declaration.
- The accessibility you declare for the element.

Use care when you define variables with the same name but different access, because doing so can lead to unexpected results. 

### See Also
[Levels of Scope](ecrConLevelsofScope.html) 
