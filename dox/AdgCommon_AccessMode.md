---
title: AccessMode

Id: AdgCommon_AccessMode

---

### ASNA.DataGate.Common.AccessMode
<table class="dtTABLE" id="Table3" cellspacing="0">
                        <colgroup span="1" class="normal">
                            <col align="middles" span="1" style="FONT-WEIGHT: bold" width="20%" />
                            <col span="1" width="69.99%" />
                            <col align="middles" span="1" width="10%" />
                        </colgroup>
                        <tbody>
                            <tr>
                                <th colspan="1" rowspan="1"> AccessMode</th>
                                <th colspan="1" rowspan="1"> Description</th>
                                <th colspan="1" rowspan="1"> Value</th>
                            </tr>
                            <tr>
                                <td colspan="1" rowspan="1">Arrival </td>
                                <td colspan="1" rowspan="1">Records are read from the file in relative record order (where supported). </td>
                                <td colspan="1" rowspan="1">2 </td>
                            </tr>
                            <tr>
                                <td colspan="1" rowspan="1" style="height: 23px">Change </td>
                                <td colspan="1" rowspan="1" style="height: 23px">Records in the file may be updated (changed). </td>
                                <td colspan="1" rowspan="1" style="height: 23px">4 </td>
                            </tr>
                            <tr>
                                <td colspan="1" rowspan="1">Delete </td>
                                <td colspan="1" rowspan="1">Records in the file may be deleted. </td>
                                <td colspan="1" rowspan="1">8 </td>
                            </tr>
                            <tr>
                                <td colspan="1" rowspan="1">CacheWrites</td>
                                <td colspan="1" rowspan="1">

A file’s data buffers are not written immediately to disk after each Add, Delete or Update operation. The target machine's inherent caching is enabled.
</td>
                                <td colspan="1" rowspan="1">32</td>
                            </tr>
                            <tr>
                                <td colspan="1" rowspan="1">Write</td>
                                <td colspan="1" rowspan="1">New records may be added to the file.</td>
                                <td colspan="1" rowspan="1">64</td>
                            </tr>
                            <tr>
                                <td colspan="1" rowspan="1">OutPut</td>
                                <td colspan="1" rowspan="1">Reserved for future use.</td>
                                <td colspan="1" rowspan="1">76</td>
                            </tr>
                            <tr>
                                <td colspan="1" rowspan="1">WriteCache </td>
                                <td colspan="1" rowspan="1">Only new records may be added to a file and they are not written immediately to disk after each Add operation. The target machine's inherent caching is enabled.</td>
                                <td colspan="1" rowspan="1">96</td>
                            </tr>
                            <tr>
                                <td colspan="1" rowspan="1">OutPutCache</td>
                                <td colspan="1" rowspan="1">Reserved for future use.</td>
                                <td colspan="1" rowspan="1">108</td>
                            </tr>
                            <tr>
                                <td colspan="1" rowspan="1">Read</td>
                                <td colspan="1" rowspan="1">Records may be read from the file.</td>
                                <td colspan="1" rowspan="1">128</td>
                            </tr>
                            <tr>
                                <td colspan="1" rowspan="1">ReadWrite</td>
                                <td colspan="1" rowspan="1">Records may be read from the file and new records may be added. (Read + Write).</td>
                                <td colspan="1" rowspan="1">192</td>
                            </tr>
                            <tr>
                                <td colspan="1" rowspan="1">RWCD</td>
                                <td colspan="1" rowspan="1">Records in the file may be read, updated, deleted and added. (Read + Change + Delete + Write).</td>
                                <td colspan="1" rowspan="1">204</td>
                            </tr>
                            <tr>
                                <td colspan="1" rowspan="1">ReadWriteCache</td>
                                <td colspan="1" rowspan="1">Records may be read from the file and new records may be added. The target machine's inherent caching is enabled for added records. (Read + Write + CacheWrites).</td>
                                <td colspan="1" rowspan="1">224</td>
                            </tr>
                            <tr>
                                <td colspan="1" rowspan="1">RWCDCache</td>
                                <td colspan="1" rowspan="1">Records in the file may be read, updated, deleted and added. The target machine's inherent caching is enabled for added, deleted and changed records. (Read + Change + Delete + Write + CacheWrites).</td>
                                <td colspan="1" rowspan="1">236</td>
                            </tr>
                            <tr>
                                <td colspan="1" rowspan="1">PrintPreview</td>
                                <td colspan="1" rowspan="1">PrinterFile output can be previewed prior to printing.</td>
                                <td colspan="1" rowspan="1">256</td>
                            </tr>
                        </tbody>
</table>

### Requirements
**Namespace:** [ASNA.DataGate.Client](../../DCS/_HYML/dcsDataGateClientNamespace.html) 

**Platforms:** Windows server 2012, Windows server 2012 R2, Windows Server 2016, Windows 7, Windows 8, Windows 10. 

**Assembly:** ASNA DataGate Client (in ASNA.DataGate.Client.dll) 
