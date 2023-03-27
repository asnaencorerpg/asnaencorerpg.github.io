---
title: Using the InfSR keyword

Id: aerConInfSRKeyword
TocParent: aerConDataGatePrintFileOverview
TocOrder: 100


---

As of 2017, the file declaration commands for DB files, print files, and workstation files have been enhanced with the ```INFSR``` keyword (last position). This keyword supports the automatic calling of a parameterless subroutine when a file operation fails. 
<pre>DclDiskFile … UseKeyBufer(…) InfSR(…)
DclPrintFile … IndDS(…) InfSR(…)
DclWorkStnFile … IndDS(…) InfSR(…)</pre>

The default value is ```‘not given’```.

When used, ```InfSR``` indicates the subroutine that is called when a file error occurs in a file operation that is NOT using an error indicator. For example, an error here will invoke ```InfSR``` (if given): 
<pre>Chain Customerl1 Key(CmCustNo)</pre>

While an error here will **not** call ```InfSR``` but will set ```*IN33``` instead:
<pre>Chain Customerl1 Key(CmCustNo) Err(*in33)</pre>

In RPG the ```INFSR``` subroutine specifies where to continue execution as an optional Factor 2 in the ```ENDSR``` command, using either a character constant or a character field containing a special value that indicates the point in the cycle where execution should continue. In ECR, instead of using ```ENDSR``` with Factor 2, you explicitly code a throw of the ```ASNA.VisualRPG.Runtime.InfSrException```. The argument to the exception describes the point in the cycle where the program execution should continue. ```*CANCEL``` terminates the program, and <blanks> re-throws the file exception. In case of <blanks> it is not necessary to code the ```InfSrException``` throw. See the table for accepted values: 
<table>
            <tr><th>RPG values in ENDSR Factor 2</th>	<th colspan="2">ECR exception arguments</th></tr>
            <tr><td>*DETL</td>	<td>"*DETL"</td>	<td>ASNA.VisualRPG.Runtime.InFSrReturnPoint.StarDetL</td></tr>
            <tr><td>*GETIN</td><td>	"*GETIN"</td><td>	ASNA.VisualRPG.Runtime.InFSrReturnPoint.StarGetIn</td></tr>
            <tr><td>*TOTC</td><td>	"*TOTC"	</td><td>ASNA.VisualRPG.Runtime.InFSrReturnPoint.StarTotC</td></tr>
            <tr><td>*TOTL</td><td>	"*TOTL"	</td><td>ASNA.VisualRPG.Runtime.InFSrReturnPoint.StarTotL</td></tr>
            <tr><td>*OFL</td><td>	"*OFL"	</td><td>ASNA.VisualRPG.Runtime.InFSrReturnPoint.StarOfL</td></tr>
            <tr><td>*DETC</td><td>	"*DETC"	</td><td>ASNA.VisualRPG.Runtime.InFSrReturnPoint.StarDetC</td></tr>
            <tr><td>*CANCL</td><td>	"*CANCL"</td><td>	ASNA.VisualRPG.Runtime.InFSrReturnPoint.StarCancel</td></tr>
            <tr><td>Blanks (factor 2 not specified)</td><td>	<not required></td><td>	<not required></td></tr>
</table>

#### Example:
<pre>dclDiskFile CMastNewL1 File("Examples/CMastNewL1") Type(*input) DB( myDb ) Designation(*primary) Org(*indexed) InfSR(MastNewErrSR)

...

BegSr MastNewErrSR
  Console.Writeline("File error!!!!")
  throw *new ASNA.VisualRPG.Runtime.InfSrException( ASNA.VisualRPG.Runtime.InFSrReturnPoint.StarTotC )
EndSr</pre>

If a field is used in factor 2, the corresponding ECR expression is 
<pre>throw *new ASNA.VisualRPG.Runtime.InfSrException( <field name> )</pre>

If the field contains blanks the ECR runtime will correctly re-throw the file exception as the RPG semantics specifies.

#### Example:
<pre>BegSr MastNewErrSR
    DclFld retPoint *string
    if CMCustNo > 100 
        retPoint = "*DETC"
    else
        retPoint = ""
    endif
    throw *new ASNA.VisualRPG.Runtime.InfSrException( retPoint )
EndSr</pre>

