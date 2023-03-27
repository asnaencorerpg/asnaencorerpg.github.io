---
title: Classes vs. Standard Programs

Id: aerTourClassesvsStandardPrograms
TocParent: aerTourUnderstandingClassesMain
TocOrder: 10


---

Classes and programs are reference types that encapsulate items defined within, but they differ in how these items are accessed from other procedures. 

The main difference between classes and programs is that **classes can be instantiated** and standard programs cannot. Because there is never more than one copy of a standard program's data, when one part of your program changes a public variable in a standard program, any other part of the program gets the same value if it subsequently reads that variable. On the other hand, Class data exists separately for each instantiated object. 

Classes and programs also employ different ```Access``` for their members. Members defined within a class are scoped within a specific instance of the class, and exist only for the lifetime of the object. The result is that to access class members from outside a class, you must use only fully qualified names; for example, <code class="ce">Object.Member```. Members declared within a standard program, on the other hand, are shared by default, and are scoped to the declaration space of the standard module's containing namespace. This means that public variables in a standard module are effectively **global variables** because they are visible from anywhere in your project, and they exist for the life of the program. Unlike class members, members of standard modules are implicitly shared and cannot use the ```Shared``` keyword. 

### See Also
[Shared Members](ecrTourSharedMembers.html)

[Understanding Classes<br />](ecrTourUnderstandingClassesMain.html) 
