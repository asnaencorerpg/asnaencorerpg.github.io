---
title: BEGCONSTRUCTOR

Id: BEGCONSTRUCTOR
TocParent: aerLrfOpCodesMain
TocOrder: 50


---

Declares the start of a constructor for the class.

```c
BEGCONSTRUCTOR
Shared (*<u>NO</u> | *YES)
Access (<u>*PRIVATE</u> | *INTERNAL | *PROTECTED | *PUBLIC)
Base (<u>*DFT</u> | Expression 1, Expression 2, ...) 
This (Argument1, Argument2, ...)      
Attributes (Attribute 1, Attribute 2, ...)
```

### Parameters

#### Shared

Optional. Declares whether the constructor is a class constructor or an instance constructor. *NO is the default.

- *NO (default) - declares an *instance* constructor, used to initialize an instance (that is, an object) of a class.
- *YES - declares a *class* constructor, not associated with an object but with the class itself. A class constructor must not define parameters.

#### Access

Optional. Allows the member to be accessible to the 'outside world'. *PRIVATE is the default.

- *PRIVATE (default) - constructor is declared and accessible only in the current class.
- *INTERNAL constructor is accessible by the whole assembly (all the classes in the same dll or exe).
- *PUBLIC constructor is accessible by everybody.
- *PROTECTED - constructor is accessible only by the current class and classes that extend the current class.

Protected members are not as private as private members,which are accessible only to members of the class in which they are declared, but they are not as public as public members, which as accessible in any function.

#### Base

Optional. Only valid in instance constructors. Calling the current constructor will also invoke the constructor in the parent class (the class the current class extends) that matches the given arguments.

- If you specify the **Base** parameter, you cannot specify the **This** parameter.
- If you do not specify **Base** or **This** , the default (*Dft) is to call the **Base** constructor (the one with no arguments)

**Note &#8211;** The **Base** constructor must exist or you will get a compiler error.

#### This

Optional. Allows a constructor to call another constructor in this same class. It contains the arguments to the other constructor. If you specify this parameter, you cannot specify the **Base** parameter.

- If you specify the **This** parameter, you cannot specify the **Base** parameter.
- If you do not specify **Base** or **This** , the default (*Dft) is to call the **Base** constructor (the one with no arguments)

**Note &#8211;** The **Base** constructor must exist or you will get a compiler error.

#### Attributes

Optional. Allows you to list one or more attributes on the constructor. To specify more than one attribute, simply separate them with commas.

Example:

```c
BegConstructor Customer Attributes(Description("Constructs an instance of the customer class"))
```

**Note &#8211;** You must provide all arguments that are defined in the attribute's constructor. Use named arguments to set the values of properties in the attribute class.

### Remarks

Constructors are special methods that allow control over initialization. Class constructors (`Shared(*Yes)`) are run after the assembly is loaded into the program memory. Instance constructors (`Shared(*No)`) run when an instance of a type is created. Instance constructors specify what happens when an object is created. Unlike other members, constructors are not inherited and do not introduce a name into a type's declaration space. Constructors may only be invoked by object-creation expressions, e.g. `*New(...)` or by the .NET framework; they may never be directly invoked.

Instance constructors must always invoke (implicitly or explicitly) a constructor in the parent class. If an instance constructor declaration does not provide neither **Base** nor **This**, then the call is implicit to the parameterless constructor in the parent class.

A **BegConstructor** routine must end with the [EndConstructor](ENDCONSTRUCTOR.html) command.

### See Also
[Custom Attributes](ecrConCustomAttributes.html)

[ENDCONSTRUCTOR](ENDCONSTRUCTOR.html)

[Using Constructors](ecrConUsingConstructors.html) 
