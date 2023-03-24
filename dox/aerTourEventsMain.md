---
title: Events

Id: aerTourEventsMain
TocParent: aerTourObjectOrientedProgrammingMain
TocOrder: 20


---

Events comprise an action which you can respond to, or "handle," in code. Events can be generated either by a user action, by program code, or by the system. 

Event-driven applications execute code in response to an event. Each form and control exposes a predefined set of events that you can program against. If one of these events occurs and there is code in the associated event handler, that code is invoked. 

The types of events raised by an object vary, but many types are common to most controls. For example, most objects will handle a **```Click```** event — if a user clicks a form, code in the form's **Click** event handler is executed. 
<blockquote class="dtBlock">
                <b class="le">Note &#8211;</b> Many events
                occur in conjunction with other events. For example, in the course of the ``` **DoubleClick** ```
                event occurring, the ``` **MouseDown** ```, ``` **MouseUp** ```, and ``` **Click** ``` events
                occur.
            </blockquote>

### See Also
[Event Subroutines](Event_Subroutines.html) 
