---
title: DCLWORKSTNFILE

Id: DCLWORKSTNFILE
TocParent: aerLrfOpCodesMain
TocOrder: 630


---

Declares an externally described workstation file for processing in a program.

```
DCLWORKSTNFILE 
Name  (name)
DspFile (<u>*NAME</u> | Character Expression)
ImpOpen(<u>*YES</u> | *NO)
RnmFmt (<u>*NONE</u> | Old Format name, New Format name, …)
Subfile(<u>*NONE</u>  | Format name, RRN name, ...)
Prefix (prefix name, [ Length ] )
Access (<u>*PRIVATE</u> | *PUBLIC | *PROTECTED | *INTERNAL)
Shared (<u>*NO</u> | *YES)
ShareOpen (<u>*NO</u> | *YES)
IndDS (Indicator DS Name)
Ignore (Format name, ...)
Include (Format name, ...)
InfSR (Subroutine Name)

```

### Parameters

**Name** 

Required. Name of the workstation file.


**DspFile** 

Optional. For ASP.Net based display files, the **DspFile** keyword names the ‘.aspx’ file containing the web form. The character expression may contain an absolute or relative path to where the file is located; for relative paths, the location of the program containing the **DclWorkStnFile** is considered the ‘current’ folder.


**ImpOpen** 

Optional. **ImpOpen** specifies if the file will be implicitly opened. The default is *YES. 

- *YES (default) - specifies that the file will automatically be opened when the program is first run. If the implicit open is unsuccessful, a run-time error will occur.
- *NO - specifies that the file will not automatically be opened when the program is first run. The RPG IV USROPN keyword is supported in Encore RPG by using **ImpOpen** (*NO).


**RnmFmt** 

Optional. **Rnmfmt** renames the external formats to new, internal formats to avoid clashes with duplicate format names. *NONE is the default. 

- For **multi** -format files, you enter the external and internal format names in pairs. All names are separated by commas.
- For **single** format files, you can either specify the internal format name as the only format name, or enter both the external and internal format names separated by a comma. 
<pre class="prettyprint">	Rnmfmt ( RCMMaster, CustInfo)                              // single format
	Rnmfmt ( CustInfo)                                         // single format
	Rnmfmt (RSubCust, CustSub, RSubSales, SalesSub)            // multi-format </pre>


**Subfile** 

Optional. The **Subfile** keyword is used to internally define the subfiles that are specified in the workstation file. The *Format name* identifies the name of the subfile record format and the *RRN name* identifies the name of the numeric field to be associated with the subfile to communicate the relative-record-number. Each subfile *format name* , with its corresponding *RRN name* , must be listed in the single **Subfile** keyword. 

The relative-record number of any record retrieved by a **READC** or **CHAIN** operation is placed into the field identified by the RRN parameter. This field is also used to specify the record number used in **WRITE** operations to the subfile. The field name specified as the rrn field parameter must be defined as numeric with zero decimal positions.


**Prefix** 

Optional. Prefix allows the specification of a string which is to be prefixed to the field names of an externally described record format. The characters specified as (prefix name) are prefixed of all fields defined in all record formats of the file. 

You can also optionally specify a numeric value (length) to indicate the number of leading characters in the existing name to be replaced. If a length is not specified or is zero, the string is prepended to the name.


**Access** 

Optional. The type of access to the workstation file. *PRIVATE is the default. 

- *PRIVATE (default) - the workstation file is accessible only from within their declaration context, including from members of any nested types, for example from within a nested procedure or from an assignment expression in a nested enumeration.
- *PUBLIC - the workstation file is accessible from anywhere within the same project, from other projects that reference the project, and from an assembly built from the project.
- *PROTECTED - the workstation file is accessible only from within the same class, or from a class derived from this class.
- *INTERNAL - the workstation file is accessible from within the same project, but not from outside the project.


**Shared** 

Optional. Shared specifies whether or not this workstation file is to be shared. *NO is the default. 

- *NO (default) - this workstation file will not be shared.
- *YES - this workstation file will be shared.


**ShareOpen** 

Optional. ShareOpen specifies if the display file (active server page) used by this **DclWorkStnFile** allows any other to refer to the same display file. Valid values are *Yes and *No. <u>*No</u> is the default. 

- *NO (default) - this display file can not be shared.
- *YES - When specifying yes, two or more programs can share the same instance of the display file, that is, one program can write records to the file, and the other can read the data provided by the user.


**IndDS** 

Optional. The name of the indicator data structure to be associated with the workstation file. The indicator data structure contains the conditioning and response indicators passed to and from data management for the file. Some basic considerations are: 

- The data structure named may be associated with more than one file.
- The data structure name must be defined by a DclDs and can be a
                        multiple-occurrence data structure.
- The length of the indicator data structure is always 99.
- The data strucure will be initialized to ***Blanks** .  To get
                        the same behavior as the IBM i, you need to manually initialize the
                        structure to (all) ***Zeros**  .<br />
 **Note** Monarch generated code accomplishes this by adding a Move
                        with ***Zeros**  to the structure's largest ***Char**  field.
- Only ***Char**  and ***Ind**  type member fields may be
                        declared.

With **ExFmt** *MyWorkStnFile* or **Read** *MyWorkStnFile* , the indicator data structure is passed in, so that the global conditioning and response indicators are not affected. Upon return from **ExFmt** or **Read** (from the WorkStnFile), the indicator data structure fields will have the response indicators values modified by the workstation file. In the example below, if the workstation file changed response indicator *IN03, the **Exit** field value is affected instead of the global *IN03; if *IN33 was changed, the **Change** field value is affected, and so forth.


**Ignore** 

Optional. The Ignore keyword allows a record format from an externally-described file to be ignored by the compiler. The external name of the record format to be ignored is specified as the parameter record format. One or more record formats can be specified, separated by commas (,) or colons (:).


Notes:


- When the program runs, the specified record format(s) will still exist in your application. All record formats contained in the file are included.
- When the Ignore keyword is specified for a file, the **Include** keyword cannot be specified.


**Include** 

Optional. The Include keyword specifies those record format names that are to be included by the compiler; all other record formats contained in the file will be ignored at compile time. For WORKSTN files, the record formats specified using the SFILE keyword are also included in the program, they need not be specified twice. Multiple record formats can be specified, separated by commas (,) or colons (:).


Notes:


- When the program runs, the record format(s) not specified will still exist in our application. All record formats contained in the file are included.
- When the Include keyword is specified for a file, the **Ignore** keyword cannot be specified.


**InfSR** 

Optional. A subroutine that is called when a file error occurs in a file operation that is NOT using an error indicator. 

- For more detail see the related Concepts page: [Using the InfSR Keyword](ecrConInfSRKeyword.html)


### Remarks
This command declares an externally described workstation file for processing in a program. 

### Example

```

 DclWorkStnFile MyWorkStnFile DspFile("./MyWorkStnFile.aspx") Subfile( CustSfl, CustRrn ) IndDS( dspind )
.	.	.
.	.	.
DclDs dspind
   DclDsFld dspindIndicators Type( *Char ) Len( 99 )
   DclDsFld Exit             Type( *Ind  ) Overlay( dspindIndicators,3 )
   DclDsFld Search           Type( *Ind  ) Overlay( dspindIndicators,4 )
   DclDsFld Previous         Type( *Ind  ) Overlay( dspindIndicators,12 )
   .	.	.
   .	.	.
   DclDsFld Change           Type( *Ind  ) Overlay( dspindIndicators,33 ) 
   .	.	.
   .	.	.
   DclDsFld Protect_Cmp      Type( *Ind  ) Overlay( dspindIndicators,99)
			
```

