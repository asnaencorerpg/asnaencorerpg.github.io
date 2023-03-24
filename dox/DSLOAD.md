---
title: DSLOAD

Id: DSLOAD
TocParent: aerLrfOpCodesMain
TocOrder: 740


---

Populates the fields of the **data structure** specified in **Name** using the **Source** parameter. 
<pre class="prettyprint">
        <span style="FONT-WEIGHT: bold">DSLOAD<br />Name </span>(DS name)<br /> **Source**  (String)<br /></pre>

### Parts

**Name** 

Required. The name of the data structure in which to populate.


**Source** 

Required. The **Source** parameter is parsed to match the lengths of each field in the data structure. The length of the string should match the total length of the fields in data structure.


### Remarks
**DSLOAD** populates the fields of the data structure specified in **Name** using the **Source** parameter. The data structure should only have fixed length fields (*Char, *Zoned, *Date, *Time, *TimeStamp, *OneChar, *Indicator). 

The Source field length must be at least as long as the sum of the fields in the data structure. If the Source length is greater than the data structure length, the excess data is ignored. If the Source length is less than the data structure length, an exception is thrown and the DSLOAD is unsuccessful. 

Character fields should be padded with the proper amount of spaces and zoned fields should be padded with zeros to match the size of the data structure field. Make sure there are no special characters in the string for numbers (e.x. + or - etc...). 

### Example

```
DclDs myDs
   DclDsFld myDSChar *Char Len(6)
   DclDSFld myDSZoned  *Zoned len(5, 2)
   DclDSFld myDSIndicator *Ind
     myDSChar = "Hello"
     myDSZoned = 987.65
     myDSIndicator = *Off **DSLoad**  Name(myDS) source(myString)
   Result: myString := "Hello 987650"      
```

### See Also
[DSDUMP](DSDUMP.html) 
