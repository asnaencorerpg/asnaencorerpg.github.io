---
title: ImplicitDecimal Property

Id: ImplicitDecimal_Property
TocParent: aerLrfRuntimeNamespace
TocOrder: 200


---

The **ImplicitDecimal** property, if set to True, allows you to achieve a decimal output value by just entering a value. 

```

 *file.* 
 **ImplicitDecimal = boolean**  
```

### Property Value
Boolean. Gets or sets whether the decimal value must be entered, or whether it is implied. 

### Remarks
For example, say you have a field of 5 numeric and 2 decimals (5,2) with ImplicitDecimal set to True. If you type in the number "12345", your value would actually be 123.45. This would take effect when the IODecimal field loses focus. It forces the decimal into a string of numbers based upon the definition of numeric length and decimals. 

### Requirements
**Namespace:** ASNA.VisualRPG.Runtime 

**Assembly:** ASNA Encore RPG Runtime (in ASNA.VisualRPG.Runtime.dll) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. <br /> 
