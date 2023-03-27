---
title: Generic Types Overview

Id: aerGenericTypesOverview
TocParent: aerConLanguageConceptsMain
TocOrder: 5


---

Encore RPG 8.2 and above support the consumption of generic types and generic methods, which opens the door to using all generic collection classes in the **Systems.Collections.Generic** namespace. Generics are a feature of the .NET framework, and defer the datatype until they are used. They allow the code to remain the same; however the datatype of the parameters can change with each use. 

The advantages of using generics is that they enforce type consistency at compile time; not at run-time; and eliminate the need for casting at runtime, making programming errors easier to catch. They also make it clear what type of object a generic type can handle. 

### Using Generic Types
The syntax for using generic types is:

< *type name* > ( ***Of** < *list of types* > ) 

e.g. List( ***Of** Customer) 

A generic type can be used in the following:

1. In any place a type is used in ECR; e.g. as a parent class: 

BegClass MyClass Extends( Dictionary( ***Of** *integer4, *string))<br /> 

2. As a field type, such as:

DclFld MyFld type( List **(*Of** PurchaseOrder)) 

- or- as the type of a BegFunc, DclSrParm, DclArray, etc 

### Calling Generic Types
The syntax for calling generic methods is:

< *method name* >( *Of< *list of types* >) (< *method parms* >) 

e.g. CreateList( ***Of** *integer4)( 1i, 2i, 3i, 4i) 
<span style="FONT-SIZE: 10pt; COLOR: navy; FONT-FAMILY: Arial" />

### See Also
[Setting Project Designer Properties](ecrConDataGatePrintfileOverview.html) 
