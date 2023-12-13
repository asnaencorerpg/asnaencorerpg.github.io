---
title: HEADINGSPEC

Id: HEADINGSPEC
TocParent: aerLrfOpCodesMain
TocOrder: 1120


---

**HEADINGSPEC** is migrated and defines the Heading specs of a print file. It is generated in place of an O-Specs specified with an "H", and placed after a [BEGPRINTATTR](BEGPRINTATTR.html); one for each heading. 

```
HEADINGSPEC 
 Fmt (Format name) 
Cond (Conditional indicator)
FetchOverflow (<u>*No</u>  | *Yes)      
```

### Parts

**Fmt** 

Required. Contains the name of the record format containing the header.


**Cond** 

Optional. Contains the conditional indicators. More than 1 condition can be specified using * **And** , and/or * **Not** between.


**FetchOverflow** 

Optional. Indicates if the page is full and has reached overflow. Only the overflow lines for the file are checked for output. All total lines conditioned by the overflow indicator is written.


### Example

```
BEGPRINTATTR
   headingspec   CpyHdr   cond(*in1p *or *inOF)    
   headingspec   OrdHdr   cond(*in77) fetchOverflow(*yes)
   headingspec   DetdHdr  cond(*in77) fetchOverflow(*yes)
   detailspec    PDetail  cond(*in42) fetchOverflow(*yes)
   totalspec     DetTot   cond(*inL1 *and detInd) fetchOverflow(*yes)
   totalspec     BoHdr    cond(*inL1 *and detInd *and *in43) fetchOverflow(*yes)
   detailspec    PBo      cond(*in43) fetchOverflow(*yes)
   totalspec     BoSubT   cond(*inL1 *and boInd) fetchOverflow(*yes)
   totalspec     BoTot    cond(*inL2 *and boInd) fetchOverflow(*yes)
   totalspec     OrdTot   cond(*inL2) fetchOverflow(*yes)
ENDPRINTATTR 
```

### See Also
[BEGPRINTATTR](BEGPRINTATTR.html) 

[DCLFMTCYCLEATTR](DCLDISKFILE.html) 

[DETAILSPEC](DETAILSPEC.html) 

[ENDPRINTATTR](ENDPRINTATTR.html) 

[TOTALSPEC](TOTALSPEC.html) 
