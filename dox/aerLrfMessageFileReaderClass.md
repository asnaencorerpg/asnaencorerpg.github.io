---
title: MessageFileReader Class

Id: aerLrfMessageFileReaderClass
TocParent: aerLrfRuntimeNamespace
TocOrder: 7


---

The MessageFileReader class supports a message file structure which is composed of individual text messages identified by a unique prefix and message number (ID) combination. Typical use for message files is to easily provide multiple language support, error message text, and for externalizing the text property of controls. 

For a list of all members of this type, see [MessageFileReader Members](aerLrfMessageFileReaderMembers.html). 

[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html) <br /> ASNA.VisualRPG.Runtime. **MessageFileReader** 

```
 <Serializable>
 **Syntax** 
```

### Thread Safety
This type is safe for multithreaded operations.

### Remarks
ASNA Message Files are not intended to be a replacement for Visual Studio's Dynamic properties. 

An ASNA Message File is acompilation of uniquely identified messages that can be retrieved at runtime. The **MessageFileReader** is instanced with the path of the compiled message file. The **GetMessageText** and **GetSecondMessageText** functions return first and second level text strings. 

To create a message, you can use any text editor - including the IDE - to create a text file. Each message must contain the following information. The information <u>must</u> be specified in this order. 

**Message Prefix** ..................3 characters (case insensitive) 

**Message Number(ID)** ........From 1 - 65535 

**Message severity** ..............From 00 - 99 

**First level text** ..................Any alphanumeric data 

Second level text must be entered on the line following the message details listed above. It also allows any combination of letters and numbers. 

To specify substitution text in either first- or send-level message text, enter the ampersand character (&) followed immediately by aone or two digit number. If you provide more substitution variables than the number of replacement identifiers (&1...&99), the extra variables are ignored. If you provide fewer substitution variables than the number of replacement identifiers, the identifiers are removed and no text is replaced. 

**Example:** 
<table>
            <tr><th>Prefix</th><th>Msg#</th><th>Severity</th><th>Text</th></tr>
            <tr>
                <td>VRT</td>
                <td>2034</td>
                <td>50</td>
                <td>
                    Invalid array index value: &1&nExpected array index is between 1 and
                    &2
                </td>
            </tr>
            <tr><td>VRT</td><td>2035</td><td>50</td><td>Runtime error occurred in Program &1 at Line &2: </td></tr>
            <tr><td>FRM</td><td>10</td><td>00</td><td>E&&xit</td></tr>
</table>

### 3 Character Prefix
The 3-character prefix will help you in associating, or identifying text in a message file. This prefix can be any 3 characters, and you can have more than 1 prefix in a message file. For example, you may want to use aprefix of ERR for all your error messages, or CTL for all of your Control messages, etc. The prefix is case-insensitive. 

### Message Number (ID)
The number can either be a hexadecimal number, or adecimal number.

- If you enter the number in hexadecimal, then valid numbers can be anywhere
                between 0x0000 and 0xFFFF.
- If you enter the number in decimal, then valid numbers can be anywhere between
                0 and 65535.

**Hint** : The format used should remain consistent throughout the message file. For example, to avoid duplication of numbers, do not use decimal numbers and hexadecimal numbers in the same message text file. 

Both the prefix and number are used together to identify a particular message text, so you can have duplicate numbers assigned to different prefixes. 

Any of the following entries are correct, and will generate the same number. Note that if you have duplicate numbers assigned to the same prefix, a Warning showing the prefix and message number will display when you compile the message file. 
<0x00F0<br />
            0xF0<br />
            240<br />
            00240

### Severity
This is a 2 digit numeric number that you can use to denote a level of severity to the message that you have defined. It is for your use only and is optionally returned to your application by the [GetMessageText](GetMessageTextMethod.html) method. 

### Message Text
Within the message text, you can specify access keys, the text to be retrieved, replacement text and 2 levels of message text (Level 1 and Level 2), as explained below. 

**Two levels of message text:** 

Level 1 text is usually a brief message text. It follows the severity and stops at the end of the line. 

Level 2 is extended message information. It is entered on the line immediately following Level 1 message text. All Level 2 message text must be indented by at least one space or TAB. You may start as many new lines as you wish for Level-2 message text as long as each line is indented as noted. 
**Replacement Text:**  You can specify any number of replacement text tokens
        for each message text. Replacement text is specified by a single ampersand,
        followed by the replacement number; i.e., &1, &2, … , &99.

The replacement text is replaced at run-time by the **GetMessageText** method. <p /> **Keyboard Navigation Keys:** <p /> Within the message text, you can specify access keys by entering two ampersands (&&) in front of the character you wish to assign to the access key. Typically for use with menu and button text; for example, "E<u>x</u>it" would be in the message text as "E&&xit". <p /> If you actually want an ampersand to display as part of the text, merely enter "&&&". If you want 2 ampersands to display, then you will need to enter "&&&&", and so on. <p /> **Display Text on Next Line:** <p> You can specify an (&n) anywhere in the message text for a new line just prior to the text you want to display on the next line. 

**Compiling the message file:** 

When all messages have been entered, execute the CRTMSGF.EXE file passing the text file name as the first argument and the compiled message file name as the second argument. The CRTMSGF.EXE file is located in the "\Program Files\Common Files\ASNAShared" folder. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

### See Also
[ASNA.VisualRPG.Runtime](aerLrfRuntimeNamespace.html)
[MessageFileReader Methods](aerLrfMessageFileReaderMethodsMain.html)
[GetMessageText Method](GetMessageTextMethod.html)
[GetSecondMessageText Method](GetSecondMessageTextMethod.html) 
