---
title: "*FetchOverflow Method"

Id: aerCycle_FetchOverflowMethod
TocParent: aerCycle_Overview
TocOrder: 8


---

### Description
The ```*FetchOverflow``` method is a compiler-defined, user-called method for cycle programs that indicates if the page is full and has reached overflow. 

```
 *Begsr ** 
 **FetchOverflow**  (<print file>)
```

### Remarks
The purpose of ```*FetchOverflow``` is to print those lines that are not "except" and which are conditioned by the print file overflow indicator. 

The ```*FetchOverflow(<print file>)``` parameter is the print file in which the FetchOverflow should happen. This parameter will cause ```FetchOverflow``` to happen only over those specs that belong to the print file. No other print file specs should be tested nor printed. 

The following operations occur when the overflow indicator is on and the overflow routine is fetched. 

- Only the overflow lines for the file with the fetch specified are checked for
                output.
- All total lines conditioned by the overflow indicator are written.
- Forms advance to a new page when a skip to a line number less than the line
                number the printer is currently on is specified in a line conditioned by an
                overflow indicator.
- Heading, detail, and exception lines conditioned by the overflow indicator are
                written.
- The line that fetched the overflow routine is written.

#### See Also
[```*DetailCalc``` Method](DetailCalcMethod.html)

[```*StartCycle``` Method](StartCycleMethod.html)

[```*TotalCalc``` Method](TotalCalcMethod.html)

[Cycle Overview](Overview.html)
