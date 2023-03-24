---
title: "*NoParm"

Id: starnoparm

TocParent: aerLrfFigConstantsMain
TocOrder: 12


---

The * **NoParm** special value indicates "the default value of the parameter", and is not a strict synonym of System.Reflection.Missing.Value. 

**Note –** With ECR, when using methods that have default parameters, you no longer need to use *NoParm as a placeholder to indicate that the default should be used; ECR will assume the default applies unless otherwise instructed. 

### Examples

```
dclfld conn ADODB.Connection
...
conn.Open(*noparm, *noparm, *noparm, *noparm)

//Here the *noparms will take the default values as described in the docs for the Open method:
Open(string ConnectionString = "", string UserID = "", string Password = "", int Options = -1)

//Also, *noparm will correctly match those parameters defined to be by reference (i.e. do not use *byref *noparm, just use *noparm). E.g.:
dclfld wordapp type(word.Application)
...
wordapp.documents.add(*noparm, *noparm, *noparm, *noparm)

//The *noparms will correctly match the method signature, in this case with System.Reflection.Missing.Values passed by reference:
Add(ref object Template, ref object NewTemplate, ref object 
   DocumentType, ref object Visible)
```

