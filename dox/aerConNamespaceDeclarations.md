---
title: Namespace Declarations

Id: aerConNamespaceDeclarations
TocParent: aerConNamespaces
TocOrder: 05


---

A namespace declaration (```DCLNAMESPACE```) consists of the name of the namespace member. If the namespace name is qualified, the namespace declaration is treated as if it is lexically nested within namespace declarations corresponding to each name in the qualified name. 

When dealing with the members of a namespace, it is not important where a particular member is declared. If two programs define an entity with the same name in the same namespace, attempting to resolve the name in the namespace causes an ambiguity error. 

Namespaces are by definition ***Public** , so a namespace declaration cannot include any access modifiers. 
<blockquote class="dtBlock">
            <b class="le">Note</b>   The project
            itself defines a root namespace, so any namespace defined within
            a file is
            nested within it.
        </blockquote>

### Related Section

[Namespace Concepts](aerConNamespacesConcepts.html)

Provides additional information of the concepts of declaring namespaces.


### See Also
[DCLNAMESPACE](DCLNAMESPACE.html) 
