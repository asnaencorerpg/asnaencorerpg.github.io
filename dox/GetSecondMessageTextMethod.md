---
title: GetSecondMessageText Method

Id: GetSecondMessageTextMethod
TocParent: aerLrfMessageFileReaderMethodsMain
TocOrder: 1


---

Overloaded. **GetSecondMessageText** returns second-level message data from an ASNA message file. See [MessageFileReader Class](aerLrfMessageFileReaderClass.html) for a description on how to establish a Message File. 

### Overload List
Returns the second level message text from the specified prefix and number.

```
BegFunc type( *String )  Access( *Public )
      dclSRParm prefix Type( *string )   By( *Value )
      dclSRParm id     Type( *Integer2 ) By( *Value )
```
Returns the second level message text from the specified prefix and id number, and assigns the replacement text for the symbolic placeholders put in the message file. 

```
BegFunc type( *String ) Access( *Public )
      dclSRParm prefix             Type( *string )   By( *Value ) 
      dclSRParm id                 Type( *Integer2 ) By( *Value ) 
      dclSRParm replacementValues  Type( *String )   By( *Value )  Rank( 1 ) 
```

### Parameters


The 3 character string prefix under which the requested message is
                stored.



The numeric value under which the requested message is stored.


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

    // no replacement
    MsgText2 = MsgReader.GetSecondMessageText( "ENG", 1200 )

    // replace text
    MsgText2 = MsgReader.GetSecondMessageText( "ENG, 1200, ReplText )
```

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. <br /> 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)

[MessageFileReader Class](aerLrfMessageFileReaderClass.html)

[MessageFileReader Members](aerLrfMessageFileReaderMembers.html)

[GetMessageText Method](GetMessageTextMethod.html) 
