---
title: "%XLATE Function"

Id: XLATE_Function
TocParent: Functions_overview
TocOrder: 52


---

**%XLATE** [built-in function](Functions_overview.html) translates *String* , replacing the *From* character values with the corresponding *To* character values. A *Start position* within the string can also be specified. 

```

 **%XLATE (From, To, String**   {,Start_position} **)** 
```

### Parts

**From** 

Required. A list of characters that should be replaced in the existing *String* .


**To** 

Required. A list of replacement characters which will replace the corresponding positional *From* character in *String* . For example, the first positional *From* character will be replaced by the first positional *To* character, second *From* with second *To* , etc.


**String** 

Required. The string to be translated.


**Start_position** 

Optional. The starting point in *String* where translation is to begin. The default is 1.


### Remarks
Translation will begin at the first or *Start* position and will continue from left to right. Each character within *String* is compared to all characters within *From* . If a match is found, the corresponding *To* character is replaced in String. *From* , *To* , and *String* must all be the same type. The value returned will be the same type and have the same length as *String* . 

### See Also
[Built-in Function Overview](Functions_overview.html)

[XLATE](XLATE.html) 
