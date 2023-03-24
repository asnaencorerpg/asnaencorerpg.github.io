---
title: Levels of Scope

Id: aerConLevelsofScope
TocParent: aerConDeclaredElementsScope
TocOrder: 0


---

A programming element is available throughout the region in which you declare it. All code in the same region can refer to the element without qualifying its name. 

### Namespace Scope
If you declare an element at program level using ``` **Access (*Internal)** ``` or ``` **Access(*Public)** ```, it becomes available to all procedures throughout the namespace in which the element is declared. 

Namespace access includes nested namespaces. An element available from within a namespace is also available from within any namespace nested inside that namespace. 

If your project does not contain any ``` **DCLNAMESPACE** ``` commands, everything in the project is in the same namespace. In this case, namespace access can be thought of as project access. ```* **Public** ``` elements in a program, class, or structure are also available to any project that references their project. 

### Program Scope
The single term *program level* applies equally to programs, classes, and structures. You can declare elements at this level by placing the declaration statement outside of any procedure or block within the program, class, or structure. 

When you make a declaration at the program level, the accessibility you choose determines the access. The namespace that contains the program, class, or structure also affects the access. 

Elements for which you declare ``` **Access** (* **Private)** ``` are available for reference to every procedure in that program, but not to any code in a different program. The ``` **DCLFLD** ``` statement at program level defaults to ``` **Access (*Private)** ``` if you do not use any accessibility keywords. However, it's better to make the access and accessibility more obvious by coding the ``` **Access** (* **Private)** ``` option in the ``` **DCLFLD** ``` command. 

### Procedure Scope
An element declared within a procedure is not available outside that procedure. Only the procedure that contains the declaration can use it. Elements at this level are also known as *local* elements. You declare them with the ``` **DCLFLD** ``` statement, with or without the ``` **Static** ``` keyword. 

Note that VB.NET and C# both support block scoped variables, whereas ECR does not provide this support. In ECR, independent of where a variable is declared in a procedure, that variable is available *anywhere* in that procedure. 

<b class="le">Note &#8211;</b> All local elements, even if they are ``` **Static(*YES)** ``` variables, are **private** to the procedure in which they appear. You cannot declare an element using ``` **Access(*Public)** ``` within a procedure. 

### See Also
[Accessibility](aerConDeclaredElementsScope.html)
[Characteristics of Encore RPG Declared Elements](aerConDeclaredElementCharacteristics.html)
[Declared Elements](aerConDeclaredElements.html)
[DCLFLD](DCLFLD.html)
[Lifetime](aerConDeclaredElementsLifetime.html) 
