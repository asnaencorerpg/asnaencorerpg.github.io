---
title: WITH

Id: WITH
TocParent: aerLrfOpCodesMain
TocOrder: 1770


---

Starts a WITH block. 

```
 **WITH** 
 **Value** (Expression)
```

### Parts

**Value** 

Required. Value consists of an expression that will be evaluated once, and its resulting value will be the "default" for the unqualified dotted expressions in the body of the **WITH** block.


### Remarks
**WITH** blocks allow a programmer to write a series of commands or statements on an object without having to specify the object each time. The way to write an expression using this object is with an unqualified dotted expression: 

.<member>

**WITH** blocks can be nested, but only the innermost **WITH** qualifies the unqualified dotted expressions in its body, i.e. the outer **WITH** blocks are masked inside the innermost **WITH** block. 

If the body of the **WITH** block is empty, <expression> will not be evaluated. 

**WITH** blocks must be ended with the [ENDWITH](ENDWITH.html) command. 

### Example

```
// You used to code like this:
   txtDBNme.Text            = My_Production_Database.DBname
   chkIsOpen.Checked        = My_Production_Database.Isopen
   txtLabel.Text            = My_Production_Database.Label
   txtServer.Text           = My_Production_Database.Server
   txtPort.Text             = My_Production_Database.Port
   txtUserId.Text           = My_Production_Database.User
   txtPlatform.Text         = My_Production_Database.Platform
```


```
// Now you can code the following using WITH.
 **With**  My_Production_Database
   txtDBNme.Text            = .DBname
   chkIsOpen.Checked        = .Isopen
   txtLabel.Text            = .Label
   txtServer.Text           = .Server
   txtPort.Text             = .Port
   txtUserId.Text           = .User
   txtPlatform.Text         = .Platform
 **EndWith** 
```

### See Also
[ENDWITH](ENDWITH.html) 
