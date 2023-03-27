---
title: Event Subroutine Parameters

Id: Event_Subroutine_Parameters
TocParent: Event_Subroutines
TocOrder: 5


---

Some events have parameters that tell you more specific information about the event. MouseDown, for example, passes the X and Y coordinates, and a code that tells which mouse button was pressed. 

You do not need to code all the parameters if you don't need them all. Any parameters that don't have a corresponding [DCLSRPARM](DCLSRPARM.html) statement will be ignored. 

Most event subroutine parameters are passed by **value** . Some however, are passed by **Reference** and allow you to change the value, thus affecting the behavior of the control. For example, on some controls, the KeyPress event passes the pressed character by reference, allowing you to change the value *before* the character is displayed in the control. 

The object determines whether a parameter is passed by value or by reference. If your **DCLSPARM** 's **BY** parameter conflicts with the object, you will get a compiler error. Consult the documentation to see if the parameter is passed by value or by reference. If you are still unsure, use the IDE editors to generate the parameter declarations for you. 

**Event Subroutine Parameters are Implemented for the Following Events:** 

[KeyDown](SF_KeyDown_Event.html) - 

[KeyUp](SF_KeyUp_Event.html) - 

[KeyPress](SF_KeyPress_Event.html) - 

[RecordDelete](SF_RecordDelete_Event.html) - [ASNA.VisualRPG.Windows.Controls.RecordDeleteArgs](aerLrfRecordDeleteArgsClass.html) 

[RecordNew](SF_RecordNew_Event.html) - [ASNA.VisualRPG.Windows.Controls.RecordNewArgs](aerLrfRecordDeleteArgsClass.html) 

[RecordSwitch](SF_RecordSwitch_Event.html) - [ASNA.VisualRPG.Windows.Controls.GridArgs](aerLrfGridArgsClass.html) 

### See Also
[BEGSR](BEGSR.html)

[DCLSRPARM](DCLSRPARM.html)

[KeyDown Event](SF_KeyDown_Event.html)

[KeyUp Event](SF_KeyUp_Event.html)

[KeyPress](SF_KeyPress_Event.html)

[RecordDelete Event](SF_RecordDelete_Event.html)

[RecordNew Event](SF_RecordNew_Event.html)

[RecordSwitch Event](SF_RecordSwitch_Event.html)

[ASNA.VisualRPG.Windows.Controls.RecordDeleteArgs](aerLrfRecordDeleteArgsClass.html)

[ASNA.VisualRPG.Windows.Controls.RecordNewArgs](aerLrfRecordDeleteArgsClass.html)

[ASNA.VisualRPG.Windows.Controls.GridArgs](aerLrfGridArgsClass.html) 
