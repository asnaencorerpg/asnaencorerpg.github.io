---
title: OTHER

Id: OTHER
TocParent: aerLrfOpCodesMain
TocOrder: 1300


---

Defines the start of the default group of statements for a [SELECT](SELECT.html) group. These are the statements that will be executed if all of the [WHEN](WHEN.html) conditions are False. 

```
OTHER 
        
```

### Remarks
The group of statements following the **OTHER** command must be terminated with an [END](END.html), or [ENDSL](ENDSL.html) command. 

In a **SELECT** group, the **OTHER** operation is optional. Additionally, only one **OTHER** operation can be used. The order of calculation operations in the **OTHER** group can be vacant. 

A **WHEN** operation cannot be specified after an **OTHER** operation in the same **SELECT** group. 

### Example

```
// Example of a SELECT group with WHxx and **OTHER** . If SALESType equals 1, do the 
  operations in sequence 1; if SALESType does not equal 1 and PROD_Type equals 2, 
  do the operations in sequence 2. If neither condition is true, do the operations in sequence 3.   
	SELECT
          When SALESType = 1
          :
          When PROD_Type = 2
	  :          
          OTHER
	  :
	  :

// In the following example, if SALESType equals 1, do the operations in sequence 1;
 if SALESType does NOT equal 1, and if PROD_Type=2 and SALESType<10, do the operations in sequence 2.
 If neither condition is true, do the operations in sequence 3.       
     SELECT
 	WHEN SALES
	Type = 1
        TotalSales = Sales1996
        YearSales = "1996"
        NameOfValue = "Sales"
        :
        WHEN PROD_Type = 2 *And SALESType < 10
        :
        OTHER
        :
        :
     ENDSL    
```

### See Also
[END](END.html)

[ENDSL](ENDSL.html)

[SELECT](SELECT.html)

[WHEN](WHEN.html) 
