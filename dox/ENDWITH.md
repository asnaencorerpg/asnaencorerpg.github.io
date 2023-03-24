---
title: ENDWITH

Id: ENDWITH
TocParent: aerLrfOpCodesMain
TocOrder: 960


---

Ends a [WITH](WITH.html) block.

```

 **ENDWITH** 
        
```

### Remarks
An **ENDWITH** marks the end of a **WITH** block. 

### Example

```
// You used to code like this:
txtDBNme.Text 		= My_Production_Database.DBname
chkIsOpen.Checked 	= My_Production_Database.Isopen
txtLabel.Text 		= My_Production_Database.Label
txtServer.Text 	= My_Production_Database.Server
txtPort.Text 		= My_Production_Database.Port
txtUserId.Text 	= My_Production_Database.User
txtPlatform.Text 	= My_Production_Database.Platform

// Now you can code the following using WITH. 

 **With**  My_Production_Database

txtDBNme.Text 		= .DBname
chkIsOpen.Checked 	= .Isopen
txtLabel.Text 		= .Label
txtServer.Text 	= .Server
txtPort.Text 		= .Port
txtUserId.Text 	= .User
txtPlatform.Text 	= .Platform
 **EndWith** 
```

### See Also
[WITH](WITH.html) 
