---
title: "DBFile.Overrider Property"

TocParent: aerLrfDBFilePropertiesMain
Id: arlrfDBFileClassOverriderProperty

---

<table class="TitleTable">
                <tr>
                    <td class="OH_tdRunningTitleColumn">ASNA Encore RPG Language Reference</td>
                </tr>
                <tr>
                    <td>
                        Overrider Property
                    </td>
                </tr>
</table>

<span style="font-size:11.0pt;font-family:&quot;Calibri&quot;,sans-serif; mso-fareast-font-family:Calibri;mso-fareast-theme-font:minor-latin;mso-bidi-font-family: &quot;Times New Roman&quot;;color:#1F497D;mso-ansi-language:EN-US;mso-fareast-language: EN-US;mso-bidi-language:AR-SA">Gets or sets the IDBFileOverrider for this DB file in Monarch applications.</span> 
**Namespace:** &#160;

ASNA.VisualRPG.Runtime
<br />
 **Assembly:** &#160;
                    <span sdata="assembly">ASNA.VisualRPG.Runtime</span> (in ASNA.VisualRPG.Runtime.dll) Version: 16.0.26.0

## Syntax

---

<a href="#"
                                       onclick="javascript:ChangeTab(&#39;ID0ECFCAAAAA&#39;,&#39;C#&#39;,&#39;1&#39;,&#39;4&#39;);return false;">C#</a>

<a id="ID0ECFCAAAAA_ViewColorized" href="#"
                                           onclick="javascript:ExchangeTitleContent(&#39;ID0ECFCAAAAA&#39;,&#39;4&#39;)" title="View Colorized"
                                           style="display: none">View Colorized</a>
                                        <a id="ID0ECFCAAAAA_copycode" href="#" onclick="javascript:CopyToClipboard(&#39;ID0ECFCAAAAA&#39;,&#39;4&#39;)"
                                           title="Copy to Clipboard">Copy to Clipboard</a>
                                        <a id="ID0ECFCAAAAA_PrintText" class="OH_PrintText" href="#"
                                           onclick="javascript:Print(&#39;ID0ECFCAAAAA&#39;,&#39;4&#39;)" title="Print">Print</a>

<pre>
<span class="keyword">public</span> 
<span class="identifier">IDBFileOverrider</span> 
<span class="identifier">Overrider</span> {
        [
<span class="identifier">EditorBrowsableAttribute</span>(
<span class="identifier">EditorBrowsableState</span>.Never)]

<span class="keyword">get</span>;
        [
<span class="identifier">EditorBrowsableAttribute</span>(
<span class="identifier">EditorBrowsableState</span>.Never)]

<span class="keyword">set</span>;
 }
</pre>

<pre>
public IDBFileOverrider Overrider {
        [EditorBrowsableAttribute(EditorBrowsableState.Never)]
        get;
        [EditorBrowsableAttribute(EditorBrowsableState.Never)]
        set;
 }
</pre>

<pre>
<span class="keyword">Public</span> 
<span class="keyword">Property</span> 
<span class="identifier">Overrider</span> 
<span class="keyword">As</span> 
<span class="identifier">IDBFileOverrider</span>
        <
<span class="identifier">EditorBrowsableAttribute</span>(
<span class="identifier">EditorBrowsableState</span>.Never)> 

<span class="keyword">Get</span>
        <
<span class="identifier">EditorBrowsableAttribute</span>(
<span class="identifier">EditorBrowsableState</span>.Never)> 

<span class="keyword">Set</span>
</pre>

<pre>
Public Property Overrider As IDBFileOverrider
        <EditorBrowsableAttribute(EditorBrowsableState.Never)> 
        Get
        <EditorBrowsableAttribute(EditorBrowsableState.Never)> 
        Set
</pre>

<pre>
<span class="keyword">public</span>:
<span class="keyword">property</span> 
<span class="identifier">IDBFileOverrider</span>^ 
<span class="identifier">Overrider</span> {
        [
<span class="identifier">EditorBrowsableAttribute</span>(
<span class="identifier">EditorBrowsableState</span>::Never)]

<span class="identifier">IDBFileOverrider</span>^ 
<span class="keyword">get</span> ();
        [
<span class="identifier">EditorBrowsableAttribute</span>(
<span class="identifier">EditorBrowsableState</span>::Never)]

<span class="keyword">void</span> 
<span class="keyword">set</span> (
<span class="identifier">IDBFileOverrider</span>^ 
<span class="parameter">value</span>);
}
</pre>

<pre>
public:
property IDBFileOverrider^ Overrider {
        [EditorBrowsableAttribute(EditorBrowsableState::Never)]
        IDBFileOverrider^ get ();
        [EditorBrowsableAttribute(EditorBrowsableState::Never)]
        void set (IDBFileOverrider^ value);
}
</pre>

#### Property Value
Type:
                    <a href="arIDBFileOverriderInterface.htm" target="">IDBFileOverrider</a>
                    <br />

The override interface to use instead of the default IDBFile interface. 
<a name="seeAlsoSection">
                        <!---->
                    </a>

## See Also

---

<a href="aerLrfDBFileClass.htm" target="">DBFile Class</a>

<a href="aerLrfDBFileMembers.htm" target="">DBFile Members</a>

