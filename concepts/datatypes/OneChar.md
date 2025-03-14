---
title: "*OneChar Data Type"

---

The ***OneChar** data type is a single Unicode text character.

**For example:** 

```
dclFld CurrencySymbol type( *onechar )
CurrencySymbol = '$'     // Assume USD
Select
When Territory = "EUROPE"
    CurrencySymbol = '€'
When Territory = "JAPAN"
    CurrencySymbol = '¥'
. . . 
```

### See Also
[Data Types](ecrLrfDataTypesMain.html)

[Unicode](/concepts/ConUnicode.html) 
