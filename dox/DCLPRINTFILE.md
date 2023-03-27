---
title: DCLPRINTFILE

Id: DCLPRINTFILE
TocParent: aerLrfOpCodesMain
TocOrder: 560


---

Declares a print file for printing in a program.

```
 **DCLPRINTFILE
Name**   (Printerfile name)
 **Db**  (Database Object)
File (<u>*FILEDESC</u>  | Character Expression)
ImpOpen (<u>*YES</u>  | *NO)
RnmFmt (<u>*NONE</u> | Old Format name, New Format name, ...)     
ShareType (<u>*FILE</u> | *EXCLUSIVE | *EXCLUSIVEREAD | *SHAREUPDATE | *SHARENOUPDATE | *SHAREREAD |
           Character Expression) 
ChkFmtId (<u>*SAME</u>  | *IGNORE | *MAP | *YES | *NO | Indicator Expression)
Prefix (prefix name, [Length]) 
OverFlowInd (Indicator-name)
IndDS (Indicator DS Name)
InfSR (Subroutine Name)
UsesPageFlds (<u>*NO</u> | *YES)
Access (<u>*PRIVATE</u> | *PUBLIC | *PROTECTED | *INTERNAL)
Shared (<u>*NO</u> | *YES)
```

### Parts

**Name** 

Required. **Name** can contain either:

- The name of the variable already defined.
- A string literal, which defines an *OBJECT variable of a particular type. The string literal must represent:
- a valid program id registered on your system at compile time.
- a valid class id registered on your system at compile time.
- a valid interface name registered on your system at compile time.

- A name of the form **Library.Object** , where Library is the name of one of the libraries selected in the new object libraries dialog, and Object is valid object name within that library.

**Note** : Using the DclDiskFile ** *name* ** , you can then get to its **fields** and **properties** . Please note that methods are reserved for use by the ASNA.Encore RPG compiler, so use the corresponding Encore RPG command if applicable. See [PrintFile Class Members](ecrLrfPrintFileMembers.html) for a listing of available members.


**Db** 

**Required** . **Db** specifies the Database Object declaration whose DBName specifies where the compiler will acquire the file description. **DB** specifies the Database Connection to use when opening the file at run-time. Database Objects are defined with the [DCLDB](DCLDB.html) command.


**File** 

Optional. **File** specifies the Library and File to use when opening the file at run-time. 

If the **File** parameter is not given, the same file that was used to retrieve the description will be opened at run-time. 

If a file name is given on the **File** parameter, that file will be accessed and must have the same description as the file accessed in the **Name** parameter, otherwise unpredictable results may occur. The **File** parameter accepts a variable as a parameter, so that the file accessed can be overridden at run-time.


**ImpOpen** 

Optional. **ImpOpen** specifies if the file will be implicitly opened. The default is *YES.

- *YES (default) - specifies that the file will automatically be opened when the program is first run. If the implicit open is unsuccessful, a run-time error will occur.
- *NO - specifies that the file will not automatically be opened when the program is first run. The RPG IV USROPN keyword is supported in Encore RPG by using Impopen(*NO).


**RnmFmt** 

Optional. Rename Format. Renames the old format to a new format, to avoid clashes with duplicate format names. *NONE is the default. 

For single format files, you can specify **RnmFmt** ( *New Format Name* ) - which will automatically rename the only format in the file to the *New Format Name* . If you specify the syntax " *Old format Name, New Format Name"* for single format files, the Encore RPG compiler will ignore the *Old Format Name* .


**ShareType** 

Optional. **ShareType** defines values on how a file will be shared. The default is *FILE. 

- *File (default) - maintains the same share type specified when the file was
                        created.
- *Exclusive - open for update, exclusive lock.
- *ExclusiveRead - open for update, other jobs may read.
- *ShareUpdate - open for update, other jobs may read or update.
- *ShareNoUpdate - open for read, other jobs may read.
- *ShareRead - open for read, other jobs may read or update.


**ChkFmtId** 

Optional. **ChkFmtId** checks if the format ID of the file at run-time compares to the format ID of the file at compile-time. Visual RPG stores the format of file(s) when a program is first compiled. At run-time, Encore RPG compares the format ID that was stored during the compilation with the current format ID. The comparing of format ID's can be especially useful when checking if new fields have been added to a file used by a program that has been compiled months ago.


- ***SAME** (default) - indicates that the run-time and compile-time format ID's **will be compared** to verify that they are the same. *(This is exactly the same as * **YES** in previous releases).*
- ***IGNORE -** indicates that the run-time and compile-time format ID's **will not be compared** to verify that they are the same. Encore RPG will use the compile-time format ID. *(This is exactly the same as ***NO** in previous releases).*

**Note:** Please be extremely careful in using *IGNORE, as it has the risk of the corruption of data files and misbehavior of your application!! 

- ***MAP** - indicates that the run-time and compile-time format ID's will be compared, and Encore RPG will accommodate non-key fields added and changed **regardless** of where they are defined in the new record format. When the modified file is opened, Encore RPG will rebuild, or **map** its compiled record format at run-time to equal that of the new record format.
- ***YES** - See * **SAME** above.
- ***NO -** See * **IGNORE** above.

Restrictions apply to non-key fields depending upon the mode of file processing and the changes made to the file as illustrated by the **table below** . The rule of thumb is that Encore RPG will process the file provided there is **no loss of data** . 

Any change in the count, order or type of Key fields is not allowed, except that a numeric key may be changed from packed to zoned and vice versa, as long as the precision remains unchanged.


**Prefix** 

Optional. **Prefix** allows the specification of a string which is to be prefixed to the field names of an externally described record format. The characters specified as (prefix name) are prefixed of all fields defined in all record formats of the file. 

You can also optionally specify a numeric value (length) to indicate the number of leading characters in the existing name to be replaced. If a length is not specified or is zero, the string is prepended to the name.


- The total Length of a name after applying the prefix must not exceed the maximum length of an RPG field name.
- If a Length is specified, it must be a numeric constant containing a value between 0 and 13 with no decimal places. Specifying a value of zero is the same as not specifying a length at all.
- The Length parameter must not be greater than or equal to number of characters in the name to be prefixed. That is, the resulting name cannot be the same as the prefix string after the prefix is applied.


**OverFlowInd** 

Optional. **OverFlowInd** contains the name of an indicator used to specify if the print file has reached the Overflow area. The indicator-name must be a previous declared field of Type (*Ind). After each ‘write’ to the print file, the cursor is positioned in the overflow area (line number as defined by the .NET Print file). The indicator named will then be set on (*ON), and the program may then test for the indicator specified to Write to other formats, such as Page Headers. Page Headers, or other formats should include properties to start a new page before printing, causing the cursor to be positioned outside the overflow area, ready for the next Write. For the next ‘write’ that is not within the overflow area, the indicator named will be turned off (*OFF).


For Monarch programs migrated using the RPG Cycle, the indicators ***INOA - *INOG and *INOV** are supported. These overflow indicators condition the lines to be printed when overflow occurs on a program described printer file. See [Overflow Indicators](ecrCycle_OverflowIndicators.html) for more information.


**IndDS** 

Optional. The name of the indicator data structure to be associated with the print file. The indicator data structure contains the conditioning and response indicators passed to and from data management for the file. Some basic considerations are: 

- The data structure named may be associated with more than one file.
- The data structure name must be defined by a DclDs and can be a
                        multiple-occurrence data structure.
- The length of the indicator data structure is always 99.
- The data strucure will be initialized to ***Blanks** .  To get
                        the same behavior as the IBM i, you need to manually initialize the
                        structure to (all) ***Zeros**  .<br />
 **Note** Monarch generated code accomplishes this by adding a Move
                        with ***Zeros**  to the structure's largest ***Char** field.
- Only ***Char**  and ***Ind**  type member fields may be
                        declared.

The indicator data structure is passed into the called application, so that the global conditioning and response indicators are not affected. Upon return, the indicator data structure fields will have the response indicators values modified. referring to the third example shown below, if the application changed response indicator *IN03, the **Exit** field value is affected instead of the global *IN03; if *IN33 was changed, the **Change** field value is affected, and so forth.


**UsesPageFlds** 

Optional. Specifies whether or not this printfile uses PAGE fields. *NO is the default. 

- *NO (default) - PAGE fields are not used.
- *YES - PAGE fields are used and will be automatically declared by the compiler.


**Access** 

Optional. The type of access to the member. *PRIVATE is the default. 

- *PRIVATE (default) - the member is accessible only from within their declaration context, including from members of any nested types, for example from within a nested procedure or from an assignment expression in a nested enumeration.
- *PUBLIC - the member is accessible from anywhere within the same project, from other projects that reference the project, and from an assembly built from the project.
- *PROTECTED - the member is accessible only from within the same class, or from a class derived from this class.
- *INTERNAL - the member is accessible from within the same project, but not from outside the project.


**Shared** 

Optional. Shared specifies whether or not this file is to be shared. *NO is the default. 

- *NO (default) - this file will not be shared.
- *YES - this file will be shared.


**InfSR** 

Optional. A subroutine that is called when a file error occurs in a file operation that is NOT using an error indicator. 

- For more detail see the related Concepts page: [Using the InfSR Keyword](ecrConInfSRKeyword.html)


### Remarks
**DCLPRINTFILE** declares a DataGate printfile for printing at run-time. At compile time, the description of the file is read in with its record format. The file name and each record format name must be unique. 

The **Name** parameter is **required** and contains the name of the print file. Using the printerfile ** *name* ** , you can then get to its **fields** and **properties.** Please note that **methods** are reserved for use by the ASNA.Encore RPG compiler, so use the corresponding Encore RPG command when applicable. See [PrintFile Class Members](ecrLrfPrintFileMembers.html) for a listing of available members. 

Print Files are always opened for sequential output operation. 

The actual file/member that is accessed at run-time is determined by the **Db** and **File** parameters. They accept a variable as a parameter, so that the file accessed can be overridden at run-time. 

When printing to an OLE DataGate Print File (COM version created with DataGate Print File Manager) from non-windows Form class, you must apply the STAThread attribute to the entry point method (the Main() method in ECR, C# and Visual Basic). This attribute indicates that the COM threading model for the application is single-threaded apartment (STA). 

If you are printing from a Windows Form class, ECR applies this attribute when it automatically creates BegSR Main at runtime. However, if you write your own BegSR Main, then you must be certain to apply the STAthread attribute. 

When printing to a .NET DataGate Print File (.NET version created with Visual Studio Print File Designer), the STAthread attribute is not required. Application of the STAThread attribute has no affect on .NET Print File printing. See Example below. 

BegSR Main Shared(*Yes) Access(*public) Attributes( STAThread() ) // ECR allows omission of "Attribute" 

BegSR Main Shared(*Yes) Access(*public) Attributes( STAThreadAttribute() ) 

### Examples

```
DclPrintFile Name(SalesRept) ImpOpen(*NO) File("*LIBL/CustReport") DB(ProdDB)

// File description is "*LIBL/CustReport" 
DclPrintFile Name(CustReport) ImpOpen(*NO) DB(DBSQL) 

// File description is "TestLib/InvReport" and the Indicator Data Structure is dspind 
DclPrintFile Name(Inventory) ImpOpen(*NO) DB(DBSQL) File("TestLib/InvReport")  IndDS( dspind )      
 . . .
 DclDs dspind
   DclDsFld dspindIndicators Type( *Char ) Len( 99 )
   DclDsFld **Exit**              Type( *Ind  ) Overlay( dspindIndicators,3 )
   DclDsFld Search           Type( *Ind  ) Overlay( dspindIndicators,4 )
   DclDsFld Previous         Type( *Ind  ) Overlay( dspindIndicators,12 )
   . . .
   DclDsFld **Change**            Type( *Ind  ) Overlay( dspindIndicators,33 ) 
   . . .
   DclDsFld Protect_Cmp      Type( *Ind  ) Overlay( dspindIndicators,99)
			
```

### See Also
[DCLDB](DCLDB.html)

[DCLDISKFILE](DCLDISKFILE.html)

[DCLFILECONT](DCLFILECONT.html)

[PrintFile Class Members](ecrLrfPrintFileMembers.html) 
