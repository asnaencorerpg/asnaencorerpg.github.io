---
title: "%OPEN Function"

Id: OPEN_Function
TocParent: Functions_overview
TocOrder: 34


---

<span style="FONT-WEIGHT: bold">%OPEN</span> [built-in function](Functions_overview.html) returns **True** if the specified file is open. 

```

 **%OPEN (File_name)** 
        
```

### Parts

**File_name** 

Required. The name of the file.


### Remarks
A file is considered "open" if it has been opened by the RPG program during initialization or by an **OPEN** operation, and has not subsequently been closed. 

If the file is conditioned by an external indicator and the external indicator was off at program initialization, the file is considered closed, and **%OPEN** returns **False** . 

### Example
<pre class="prettyprint"><code class="language-aer">// This goes in main line code
DclDiskFile Name( CUSTMAST ) Type( *Input ) Org( *Indexed ) DBDesc ( "ASNA LOCAL DB" )
MsgBox %OPEN ( CUSTMAST )
Close File   ( CUSTMAST )
MsgBox **%OPEN**  ( CUSTMAST )
ENDSR      ```?</pre>

### See Also
[Built-in Function Overview](Functions_overview.html)
[IsOpen Property](IsOpen_Property.html) 
