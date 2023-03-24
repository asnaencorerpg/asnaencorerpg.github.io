---
title: File Processing

Id: File_Processing
TocParent: aerLrfLangElementsMain
TocOrder: 0


---

File processing in Encore RPG is no different than in RPG/400. Extensions to incorporate client/server processing have been added in the [DCLDISKFILE](DCLDISKFILE.html) statement. An application can dynamically open and process database files and members from specific databases defined at run-time. The database, file and member can be defined as variables. 

**DBDESC & FILEDESC** - Because the file name (FileName) is a variable, the compiler must be provided the name of the file and its database paths where the file description is located. The DBDESC and FILEDESC parameter values must be literals. 

**DB** - Database name is the variable into which the application will identify the database location of the file before opening the file. Values may be *NONE (defaults to *LOCALDFT), *SYSDFT (defaults to *REMOTEDFT), a literal database name, or a variable database name identifying the client/workstation Acceler8DB database, server Acceler8DB database or AS/400 database name. 

**FILE** - File name is the variable into which the application will identify the file's path before opening the file. 

**MBR** - Member name is the variable into which the application will identify the file member before opening the file. 

**Various sources are available to the program to acquire the file name.** 

[DCLPLIST](DCLPLIST.html) - The file, member and database names may be passed as a parameter in the program startup command line. For example: C:\MyProg.exe "ProdLib/SalesHist" Sales1990 *REMOTEDFT 

**Data** - The names may originate as data from another file. 

**User** - The names may originate from a user entry or as a selection from a Subfile, OptionButton, Check Box, ListBox or ComboBox. 

### See Also
[DCLDISKFILE](DCLDISKFILE.html)
[DCLPLIST](DCLPLIST.html) 
