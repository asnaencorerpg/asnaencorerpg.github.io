---
title: DCLCONST

Id: DCLCONST
TocParent: aerLrfOpCodesMain
TocOrder: 380


---

Declares a named constant. By definition, constants are shared members and can be declared at the class level, and can also be declared locally to methods. 

```

 **DCLCONST
Name** (Character Expression)
 **Value**  (Constant Expression)
Access (<u>*PRIVATE</u> | *PUBLIC | *PROTECTED | *INTERNAL)
```

### Parts

**Name** 

Required. The name of the constant.


**Value** 

Required. The expression of the constant.


**Access** 

Optional. The type of access to the member. *PRIVATE is the default.

- *PRIVATE (default) - access to the member is accessible only from within their declaration context, including from members of any nested types, for example from within a nested procedure or from an assignment expression in a nested enumeration.
- *PUBLIC - access to the member is accessible from anywhere within the same project, from other projects that reference the project, and from an assembly built from the project.
- *PROTECTED - access to the member is accessible only from within the same class, or from a class derived from this class.
- *INTERNAL - access to the member is accessible from within the same project, but not from outside the project.


### See Also
[Constant Expression](Constant_Expression.html)
[DCLFLD](DCLFLD.html)
[Literals](aerLrfLiteralsMain.html) 
