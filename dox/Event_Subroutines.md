---
title: Event Subroutines

Id: Event_Subroutines
TocParent: aerLrfLangElementsMain
TocOrder: 70


---

When a program recognizes that an event has occurred, it automatically invokes the event subroutine with the name that corresponds to the event. Because the name establishes an association between the object and the code, event subroutines are said to be attached to forms and controls. 

An event subroutine for a control or form combines the object's actual name (specified in the Name property) and the event name. For instance, if you want a CommandButton named ExitButton to invoke an event subroutine when it is clicked, use the subroutine: 

BEGSR ExitButton Click 

### See Also
[Declarations](Declarations.html)

[General Subroutines](General_Subroutines.html)

[Mainline Code](Mainline_Code.html) 
