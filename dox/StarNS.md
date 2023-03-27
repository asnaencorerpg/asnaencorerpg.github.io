---
title: "*NS"

Id: StarNS
TocParent: aerLrfFigConstantsMain
TocOrder: 11


---

*NS is a figurative constant that represents the name of the current namespaces as a string, ending with a dot ".". 

### Remarks
Use the [DCLNAMESPACE](DCLNAMESPACE.html) command to declare a particular namespace in code. 

It is used most commonly in conjunction with [CALLD](CALLD.html) where the program to call has the same namespace as the caller: 
<code class="language-aer">CALLD Pgm(*NS + "OtherPgm")```

### See Also
[Figurative Constants](aerLrfFigConstantsMain.html)

[CALLD](CALLD.html)

[DCLNAMESPACE](DCLNAMESPACE.html) 
