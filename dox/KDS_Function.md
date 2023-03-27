---
title: "%KDS Function"

Id: KDS_Function
TocParent: Functions_overview
TocOrder: 26


---

**%KDS** [built-in function](Functions_overview.html) is allowed as the search argument for any keyed input or output operation ([CHAIN](CHAIN.html), [DELETE](DELETE.html), [READE](READE.html), [READPE](READPE.html), [SETGT](SETGT.html), [SETLL](SETLL.html)). The search argument is specified by the subfields of the data structure name coded as the first argument of the built-in function. 

```

 **%KDS (DSN_name**  {, Number-keys} **)** 
```

### Parts

**DSN_name** 

Required. Contains the name of the data structure.


**Number-keys** 

Optional. Contains the number of subfields of the data structure to use as the search argument.


### Remarks
The individual key values in the compound key are taken from the top level subfields of the data structure. 

Subfields used to form the compound key must not be arrays.

The types of all subfields (up to the number specified by ***Number-keys*** ) must match the types of the actual keys. Where lengths and formats differ, the value is converted to the proper length and format. 

If the data structure is defined as a multiple occurrence data structure, an index must be supplied for the data structure. 

### Example

```
DclDb       Name  ( myDB ) DBName   ( "DG NET LOCAL" )

DclDiskFile Name  ( Salesfile )           + 
            Type  ( *Input )              + 
            Org   ( *Indexed )            + 
            file  ( "*libl/CSmasterL1" )  + 
            db    ( myDB  )               + 
            impopen ( *NO ) 

dclds Saleskey1  ExtDesc(*Yes) FileDesc( "Examples/CSmasterL1" ) DBDesc( "dg net local" ) 

dclds saleskey2 
      dcldsfld    Custno      like(cscustno) 
      dcldsfld    Year  like(csyear) 
      ... 
      With saleskey1 
        .csCustno = 1200 
        .csYear   = 2006 
        .csType   = 1   
      endwith 

      chain salesfile %KDS( saleskey1 , 3 )     // use all 3 key parts 
      ... 
      saleskey2.Custno = 2400 
      saleskey2.Year    = 2008 

      Setll salesfile %KDS( saleskey2 )   
      ReadE salesfile %KDS( saleskey2 ) 
   ... 
```

### See Also
[Built-in Function Overview](Functions_overview.html)

[Multiple Occurrence Data Structures](Mult_Occur_DS.html)

[CHAIN](CHAIN.html)

[DELETE](DELETE.html)

[READE](READE.html)

[READPE](READPE.html)

[SETGT](SETGT.html)

[SETLL](SETLL.html) 
