---
title: Access Types

Id: aerConAccessTypes
TocParent: Declarations
TocOrder: 0


---

A declaration specifies the **access type** of the entity it declares. An entity's access type does not change the scope of an entity's name. 

To specify an access type, use the **Access** keyword for any of the [declaration op codes](/concepts/operation-codes/DeclarationOpCodes.html). The four access types of the **Access** keyword are `*Public`, `*Private`, `*Protected`, and `*Internal`.`*Public` is the most permissive access type, and the other three types are all subsets of `*Public`. 

The default **Access** type is `*PRIVATE`, indicating that the entity being declared will not be shared. 

- `*PRIVATE` (default) - access is accessible only from within their declaration context, including from members of any nested types, for example from within a nested procedure or from an assignment expression in a nested enumeration.
- `*PUBLIC` - access is accessible from anywhere within the same project, from other projects that reference the project, and from an assembly built from the project.
- `*PROTECTED` - access is accessible only from within the same class, or from a class derived from this class.
- `*INTERNAL` - access is accessible from within the same project, but not from outside the project.

The accessibility in a declaration does not depend on the accessibility of the declaration context. For example, a type declared with `*Private` access may contain a type member with `*Public` access. 

### See Also

[Accessibility](/concepts/declared-elements/Accessibility.html)

[Declaration Op Codes](/concepts/operation-codes/DeclarationOpCodes.html) 
