---
title: Accessibility

Id: aerConAccessibility
TocParent: aerConDeclaredElements
TocOrder: 3


---

The *accessibility* of a declared element is the ability to use it, that is, the permission for code to read it or write to it. This is determined not only by how you declare the element itself, but also by the accessibility of the element's container. If the containing element is not accessible, none of its contained elements are accessible, even those declared as **Access** (* **Public** ). For example, a ***Public** variable in a ***Private** structure is accessible from inside the class containing the structure, but not from outside that class. 

### Public
The **Access (*Public)** keyword in the **DCLFLD** statement declares elements to be accessible from anywhere within the same project, from other projects that reference the project, and from an assembly built from the project. The following code shows a sample **Public** declaration: 

```
DclFld MyField Type( *String ) Len (4) Access( *Public ) 
```

You can use * **Public** only at module, namespace, or file level. This means you can declare a public element in a source file or inside a class, but not within a procedure. 

### Protected
The **Access** (* **Protected)** keyword in DCLFLD declares elements to be accessible only from within the same class, or from a class derived from this class. The following code shows a sample **Protected** declaration: 

```
DclFld MyField Type( *String ) Len (4) Access( *Protected ) 
```

You can use **Protected** only at class level, and only when declaring a member of a class. 

### Internal
The ****Access** (*Internal<b>)** </b> keyword in the **Dim** statement declares elements to be accessible from within the same project, but not from outside the project. The following code shows a sample * **Internal** declaration: 

```
DclFld MyField Type( *String ) Len (4) Access( *Protected ) 
```

You can use ***Internal** only at namespace, or file level. This means you can declare a friend element in a source file or inside a class, but not within a procedure. 

### Private
The ****Access** (*<b>Private)** </b> keyword in DCLFLD declares elements to be accessible only from within the same module, class, or structure. The following code shows a sample * **Private** declaration: 

```
DclFld MyField Type( *String ) Len (4) Access( *Protected ) 
```

You can use * **Private** only at namespace or file level. This means you can declare a private element in a source file or inside a class, but not within a procedure. 

### See Also
[Declared Element Names](aerConDeclaredElements.html)

[Declared Element Characteristics](aerConDeclaredElementCharacteristics.html)

[Lifetime](aerConDeclaredElementsLifetime.html) 
