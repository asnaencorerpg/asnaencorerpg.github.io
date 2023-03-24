---
title: Considerations for OLE Print File Conversion

Id: aerConsiderationsforOLEPrintFileSupport
TocParent: aerConDataGatePrintFileOverview
TocOrder: 100


---

** ECR does not support OLE Print files (print files created by adbpfm.exe). ** 

OLE Print files can be converted by the .NET Print file Designer (or the Upgrade Assistant when projects were written for the "Classic" ECR). 

The .NET Print File Designer (which is now part of [DataGate Studio](..\..\DgStudio\_HTML\dgIntro.html)), allows the opening of OLE Print Files. In the process of loading the OLE Print files the controls are automatically converted to the new .NET print controls. The conversion may not be 100% effective if third party controls were used in the OLE Printfiles. 

The output window will report the conversion process, possibly issuing errors if the conversion is not complete (and the user will need to manually re-add the equivalent control). 

**Warning** &#8212; Applications written for Classic and/or ECR prior to 8.2/9.0 **will fail** at runtime if the Print files are not converted. 

### OLE Print File Conversion Utility
As an alternative to convert print files from OLE to .NET, a utility is provided to convert files in batch. This utility is called **OlePrintfileToNetPrintfile.exe,** and can be found in **C:\Program Files\Common Files\ASNAShared\Client\Printing 16.0** . 

This utility does not have a GUI, so it can only be launched from the command line. An MSDOS batch file is recommended for multiple printfile file conversions. 

### Command Line Parameters
The following are the command line required and optional parameters: 

**Required options:** 

- <code>/src -</code> Path of the OLE Print File.
- <code>/rdb -</code> Database name where <code>/src</code> is located.

**Additional options:** 

- <code>/dest -</code> Path where the converted file will be
                placed.

Default is the value of <code>/src</code>.
- <code>/wdb -</code> Database name where <code>/dest</code> will be
                placed.

Default is the value of <code>/rdb</code>.
- <code>/bak -</code>    Path to a library where original file
                will be placed.

Library is created if it does not exist.

If this switch is used, the value of <code>/dest</code> is ignored.
- <code>/wlocal</code> - Path of a file where the converted Ole Print file will
                be placed.

If this switch is used, a file is not created in the database.
- <code>/lsdb</code> -    List available database names.

**Note** &#8212; If an object exists at <code>/dest</code> in <code>/wdb</code>, the converter will overwrite it. 

The converter has the capability of accepting a file for the value of <code>/rdb</code> and/or <code>/wdb</code>. 

This file should contain a serialized Source Profile (used internally for now).

### Output to a file
When calling from a batch program, it is recommended to re-direct the output to a file to make it easier to review the batch process result. <br /> Something like the following is recommended. 

Assuming the current command prompt directory is set to "C:\Program Files\Common Files\ASNAshared\Client\Printing 16.0" 

Assuming the batch file is called **ConvertMyOlePrintfiles.bat** , the contents would look like the following: 

- <code>
                OlePrintfileToNetPrintfile /src Payroll20/PayrollReport /dest
                Payroll30/PayrollReportNet /owr MyOldDbName > result.txt
            </code>
- <code>
                OlePrintfileToNetPrintfile /src AC20/CustomerReport /dest AC30/ CustomerReport
                Net /owr MyOldDbName >> result.txt
            </code>
- <code>
                OlePrintfileToNetPrintfile /src Inv20/PartsReport /dest Inv30/PartsReport Net
                /owr MyOldDbName >> result.txt
            </code>

To start the batch process, type **ConvertMyOlePrintfiles.bat** from the command line. 

After the batch process runs, the user may edit the new ASCII file " **result.txt** " to get details about the conversion process. 
