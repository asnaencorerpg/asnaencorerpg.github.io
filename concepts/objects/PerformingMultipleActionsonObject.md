
title: Performing Multiple Actions on an Object

---

Often, you need to perform several different actions on the same object. For example, you may need to set several properties or execute several methods for the same object. 

```
 // You used to code like this: txtDBNme.Text 		= My_Production_Database.DBname
chkIsOpen.Checked 	= My_Production_Database.Isopen
txtLabel.Text 		= My_Production_Database.Label
txtServer.Text 	= My_Production_Database.Server
txtPort.Text 		= My_Production_Database.Port
txtUserId.Text 	= My_Production_Database.User
txtPlatform.Text 	= My_Production_Database.Platform

 // Now you can code the following using WITH. **With**  My_Production_Database txtDBNme.Text = .DBname
chkIsOpen.Checked 	= .Isopen
txtLabel.Text 		= .Label
txtServer.Text 		= .Server
txtPort.Text 		= .Port
txtUserId.Text 		= .User
txtPlatform.Text 	= .Platform

 **EndWith** 
      
```

**To set multiple properties for the same object** 

- One way to do this is to write several statements using the same object variable, as in the following code:

```
txtDBNme.Text = My_Production_Database.DBname 
chkIsOpen.Checked = My_Production_Database.Isopen
txtLabel.Text= My_Production_Database.Label
txtServer.Text = My_Production_Database.Server
txtPort.Text = My_Production_Database.Port
txtUserId.Text  = My_Production_Database.User
txtPlatform.Text  = My_Production_Database.Platform
```
- However, you can make this code easier to write and read by using the ```With...EndWith``` statement, as in the following code: 

```
With  My_Production_Database
    txtDBNme.Text = .DBname
    chkIsOpen.Checked = .Isopen
    txtLabel.Text = .Label
    txtServer.Text = .Server
    txtPort.Text = .Port
    txtUserId.Text = .User
    txtPlatform.Text = .Platform
EndWith    
```
- You can also nest ```With...EndWith``` commands by placing objects one inside another, as in the following code: 

```
With myHashTable()
   PicGive.Image = .Item ["Dog"]    *as Image
      myArray       = .Item ["Months"] *as String
      With Pic1
       .Image    = *Nothing
              .Enables  = *False
   EndWith
   lblGive.Font  = .Item ["Font"]   *as Font
EndWIth
```

Within the nested ```With``` statement, however, the syntax refers to the nested object; properties of the object in the outer ```With``` statement are not set. 

### See Also
[Assignment Operation Codes](/concepts/operation-codes/AssignmentOpCodes.html)

[Declaration Statements](/concepts/operation-codes/DeclarationOpCodes.html)

[Executable Operation Codes](/concepts/operation-codes/ExecutableOpCodes.html) 
