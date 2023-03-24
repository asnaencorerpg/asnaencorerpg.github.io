---
title: GetMessageText Method

Id: GetMessageTextMethod
TocParent: aerLrfMessageFileReaderMethodsMain
TocOrder: 0


---

Overloaded. **GetMessageText** returns message first-level data from an ASNA Message File. See [MessageFileReader Class](aerLrfMessageFileReaderClass.html) for a description on how to establish a Message File. 

### Overload List
Returns the message text from the specified prefix and number.

```
   BegFunc type( *String )  Access( *Public )
      dclSRParm prefix Type( *string )   By( *Value )
      dclSRParm id     Type( *Integer2 ) By( *Value )  
```
Returns the message text from the specified prefix and id number, and sets the severity byte equal to the severity level of the requested message. 

```
   BegFunc type( *String )  Access( *Public )
      dclSRParm prefix       Type( *string )   By( *Value )
      dclSRParm id           Type( *Integer2 ) By( *Value )
      dclSRParm severity     Type( *Byte )     By( *Reference ) 
```
<span> Returns the message text from the specified prefix and id number, and assigns the replacement text for the symbolic placeholders put in the message file. </span> 

```
   BegFunc type( *String ) Access( *Public )
      dclSRParm prefix             Type( *string )   By( *Value ) 
      dclSRParm id                 Type( *Integer2 ) By( *Value ) 
      dclSRParm replacementValues  Type( *String )   By( *Value )  Rank( 1 )  
```
Returns the message text from the specified prefix and id number, sets the severity byte equal to the severity level of the requested message, and assigns the replacement text for the symbolic placeholder put in the message file. 

```
   BegFunc type( *String ) Access( *Public )
      dclSRParm prefix             Type( *string )   By( *Value ) 
      dclSRParm id                 Type( *Integer2 ) By( *Value )
      dclSRParm severity           Type( *Byte )     By( *Reference ) 
      dclSRParm replacementValues  Type( *String )   By( *Value )  Rank( 1 )  
```

### Parameters


The 3 character string prefix under which the requested message is
                stored.



The numeric value under which the requested message is stored.



The
                out parameter is set to the severity level of the requested message.


replacementValues

An array of objects meant to replace the symbolic
                placeholders placed in the message file.


### Example

```
    Using ANSA.VisualRPG.Runtime
    DclFld MsgReader        Type( MessageFileReader )
    DclFld MsgSeverity      Type( *Byte )
    DclFld MsgText1         Type( *String )    // 1st level
    DclFld MsgText2         Type( *String )    // 2nd level
    DclArray ReplText       Type( *Object) Dim(20)
    DclFld MsgFileName      Type( *String) Inz("MessFile.msg")
    ReplText{0} = "Hello"
    ReplText{1} = "World"

    MsgReader = *New MessageFileReader(MsgFileName)

    // no replacement, no severity
    MsgText1 = MsgReader.GetMessageText( "ENG", 1200 )

    // no replacement, return severity by reference
    MsgText1 = MsgReader.GetMessageText( "ENG, 1200, *ByRef MsgSeverity )

    // no severity, replace text
    MsgText1 = MsgReader.GetMessageText( "ENG, 1200, ReplText )

    //return severity by reference, replace text
    MsgText1 = MsgReader.GetMessageText( "ENG", 1200, *ByRef MsgSeverity, ReplText )
```

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[MessageFileReader Class](aerLrfMessageFileReaderClass.html)
[MessageFileReader Members](aerLrfMessageFileReaderMembers.html)
[GetSecondMessageText Method](GetSecondMessageTextMethod.html) 
