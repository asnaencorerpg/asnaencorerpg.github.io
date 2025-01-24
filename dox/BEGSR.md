---
title: BEGSR

Id: BEGSR
TocParent: aerLrfOpCodesMain
TocOrder: 140


---

Identifies the beginning of a subroutine. If it is an event-handling subroutine, it also identifies the event it handles. 

** For Monarch applications ** , BEGSR identifies the beginning of a procedure, which is nested inside of a [BEGPROC](BEGPROC.html) routine. In this case, only 2 parameters are used; **Name** and **ExName** . See **Remarks** section below for more information. 

```
BEGSR 
Name  (Function name | *PSSR ) // for Monarch procedures only Event (<u>*NONE</u> | *CHANGE | event name)
Shared (<u>*NO</u> | *YES)
Access (<u>*PRIVATE</u> | *INTERNAL | *PUBLIC | *PROTECTED) 
Modifier (<u>*NONE</u> | *MUSTOVERRIDE | *NOTOVERRIDABLE | *OVERRIDABLE | *OVERRIDES) 
Implements (Interface name list) 
Attributes (attribute 1, attribute 2, ...)
 ExName (field name) //use only when Name(*PSSR) is used for Monarch procedures 
```


### Parameters

**Name** 

Required. The name of the subroutine. This must be used on an [EXSR](EXSR.html) operation to call the subroutine. Event handling subroutines are declared by specifying the name of an **EVENT** . In that case, **Name** must be the name of a form, menu option, or control declared earlier in the program. Every subroutine in a given program must contain a unique symbolic name. Only one subroutine can be defined by this name.


** For Monarch applications ** - When used inside a nested **BEGPROC** routine, Name identifies the name of the procedure. It can be either a valid ECR identifier or the special value * **PSSR** . If * **PSSR** is used, then you must also use the parameter **ExName** , which declares the field name that contains the exception trapped by the *PSSR subroutine.



Optional. The event names that are valid in **EVENT** depend upon the control being used in **Name** . In this case, *CHAR is assumed if there is one integer, and *ZONED is assumed if there are two integers.



Optional. Indicates if one or more declared programming elements are shared. **Shared** elements are not associated with a specific instance of a class or structure. You can access them by qualifying them either with the class or structure name, or with the variable name of a specific instance of the class or structure. *NO is the default, indicating that the property will not be shared. 

- *NO (default) - this property will not be shared.
- *YES - this property will be shared.


**Access** 

Optional. The type of access to the member. The default is *Private.

- *PRIVATE (default) - access to the member is accessible only from within their declaration context, including from members of any nested types, for example from within a nested procedure or from an assignment expression in a nested enumeration.
- *PUBLIC - access to the member is accessible from anywhere within the same project, from other projects that reference the project, and from an assembly built from the project.
- *PROTECTED - access to the property is accessible only from within the same class, or from a class derived from this class.
- *INTERNAL - access to the member is accessible from within the same project, but not from outside the project.


**Modifier** 

Optional. The type of access to the property. The default is *PRIVATE.

- *MUSTOVERRIDE - specifies that a property or procedure in a base class must be overridden in a derived class before it can be used.
- *NOTOVERRIDABLE - specifies that a property or procedure cannot be overridden in a derived class.
- *OVERRIDABLE - specifies that a property or method can be overridden in a derived class.
- *OVERRIDES - specifies that a property or method overrides a member inherited from a base class.


**Implements** 

Optional. Indicates that this class implements the members of an interface. An interface defines a set of properties, events and methods, but does not provide an implementation of them, just a definition. You must implement every member of every interface you specify in this keyword.


**Attributes** 

Optional. Allows you to provide one or more attributes that apply to this class. To specify more than one attribute, simply separate them with commas.


**Note &#8211;** When your project startup object is BEGSR Main and you are printing to a DataGate OLE Print File (maintained with adpfm.exe 5.41 or earlier), the following Attribute ** *must* ** be included: **System.STAThread()** .


**Example** :


BegSr Main Shared( *Yes ) Access( *Public ) Attributes( **System.STAThread** () )


**ExName** 

Optional. This parameter **must only** be used if the special value **Name (*PSSR)** was given for Monarch procedures. ExName declares the field name that contains the exception trapped by the *PSSR subroutine.


### Remarks
Parameters may be declared for a subroutine by using **DCLSRPARM** commands right after the **BEGSR** . See [DCLSRPARM](DCLSRPARM.html) for more information. 

[ENDSR](ENDSR.html) must be the last statement in the subroutine. 

** For Monarch applications: ** When used inside a nested **BEGPROC** routine, only 2 parameters are used; **Name** and **ExName** . 

- Name (Required) - identifies the name of the procedure. It can be either a valid ECR identifier or the special value * **PSSR** .
- ExName - this parameter **must only** be used if the special value **Name (*PSSR)** was given. ExName declares the field name that contains the exception trapped by the *PSSR subroutine.

### See Also
[Built-In Controls](Control_Properties.html)

[BEGFUNC](BEGFUNC.html)

[BEGPROC](BEGPROC.html)

[Custom Attributes](ecrConCustomAttributes.html)

[DCLSRPARM](DCLSRPARM.html)

[ENDSR](ENDSR.html)

[EXSR](EXSR.html) 
