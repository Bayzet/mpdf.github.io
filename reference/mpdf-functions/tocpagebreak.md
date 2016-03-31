---
layout: page
title: TOCpagebreak()
parent_title: mPDF functions
permalink: /reference/mpdf-functions/tocpagebreak.html
modification_time: 2015-08-05T12:01:12+00:00
---

<p>(mPDF &gt;= 2.0)</p>
<p>TOCpagebreak — Insert a table of contents in the document</p>

<div class="alert alert-info" role="alert"><strong>Note:</strong> A new function <a href="{{ "/reference/mpdf-functions/tocpagebreakbyarray.html" | prepend: site.baseurl }}">TOCpagebreakByArray()</a> was added in mPDF 5.0 which is recommended as much simpler to use.</div>

# Description

<p class="manual_block">void <b>TOCpagebreak</b> ([ string <span class="parameter">$font</span> [, float <span class="parameter">$font-size</span> [, int <span class="parameter">$indent</span> [, mixed <span class="parameter">$paging</span> [, mixed <span class="parameter">$links</span> [, string <span class="parameter">$toc-orientation</span> [, float <span class="parameter">$toc-margin-left</span> [, float <span class="parameter">$toc-margin-right</span> [, float <span class="parameter">$toc-margin-top</span> [, float <span class="parameter">$toc-margin-bottom</span> [, float <span class="parameter">$toc-margin-header</span> [, float <span class="parameter">$toc-margin-footer</span> [, string <span class="parameter">$toc-odd-header-name</span> [, string <span class="parameter">$toc-even-header-name</span> [, string <span class="parameter">$toc-odd-footer-name</span> [, string <span class="parameter">$toc-even-footer-name</span> [, int <span class="parameter">$toc-odd-header-value</span> [, int <span class="parameter">$toc-even-header-value</span> [, int <span class="parameter">$toc-odd-footer-value</span> [, int <span class="parameter">$toc-even-footer-value</span> [, string <span class="parameter">$toc-preHTML</span> [, string <span class="parameter">$toc-postHTML</span> [, string <span class="parameter">$toc-bookmarkText</span> [, string <span class="parameter">$resetpagenum</span> [, string <span class="parameter">$pagenumstyle</span> [, string <span class="parameter">$suppress</span> [, string <span class="parameter">$orientation </span>[, float <span class="parameter">$margin-left</span> [, float <span class="parameter">$margin-right</span> [, float $<span class="parameter">margin-top</span> [, float $<span class="parameter">margin-bottom</span> [, float $<span class="parameter">margin-header</span> [, float <span class="parameter">$margin-footer</span> [, string <span class="parameter">$odd-header-name</span> [, string <span class="parameter">$even-header-name</span> [, string $<span class="parameter">odd-footer-name</span> [, string $<span class="parameter">even-footer-name</span> [, mixed $<span class="parameter">odd-header-value</span> [, mixed <span class="parameter">$even-header-value</span> [, mixed <span class="parameter">$odd-footer-value</span> [, mixed $<span class="parameter">even-footer-value</span> [, string <span class="parameter">$name</span> [, string <span class="parameter">$pageselector</span> [, string <span class="parameter">$toc-pageselector</span> [, string <span class="parameter">$sheet-size</span> [, string <span class="parameter">$toc-sheet-size</span> [, string <span class="parameter">$outdent </span>[, int <span class="parameter">$<span class="parameter">toc-resetpagenum</span></span> [, string <span class="parameter">$</span><span class="parameter">toc-pagenumstyle</span> [, mixed <span class="parameter">$<span class="parameter">toc-suppress</span> </span>]]]]]]]]]]]]]]]]]]]]]]]]]]]]]]]]]]]]]]]]]]]]]]]]]])</p>
<p>Add a new page to the document, marking the point at which a Table of Contents (<acronym title="Table of Contents">ToC</acronym>) will be inserted in the document at the end of writing. The numerous parameters specify both paging details for the continuing document, and for the <acronym title="Table of Contents">ToC</acronym> when it is generated.</p>

<div class="alert alert-info" role="alert"><strong>Note:</strong> From mPDF 5.7 the layout of a table of contents can be controlled using CSS. <span class="parameter">font</span>, <span class="parameter">font-size</span> and <span class="parameter">indent</span> have become redundant. They are kept as parameters to allow backwards compatibility, but any values set for these are ignored.</div>

<div class="alert alert-info" role="alert"><strong>Note:</strong> When writing a <span class="smallblock">DOUBLE-SIDED</span> document, the <acronym title="Table of Contents">ToC</acronym> will always start on an <span class="smallblock">ODD</span> page. Therefore there is no option to specifiy the pagebreak <span class="parameter">type </span>as in <a href="{{ "/reference/mpdf-functions/addpage.html" | prepend: site.baseurl }}">AddPage()</a> - using <b>TOCpagebreak()</b> will always continue the document on an <span class="smallblock">ODD</span> page.</div>

<div class="alert alert-info" role="alert"><strong>Note:</strong> Page numbering is always suppressed in the <acronym title="Table of Contents">ToC</acronym>.</div>

<div class="alert alert-info" role="alert"><strong>Note:</strong> The <acronym title="Table of Contents">ToC</acronym> is generated at the end of the document. Unless otherwise specified, the <acronym title="Table of Contents">ToC</acronym> will inherit the page margins, headers/footers and orientation of the last page written to the document.</div>

<div class="alert alert-info" role="alert"><strong>Note:</strong> From mPDF 2.3 you can include more than one <acronym title="Table of Contents">ToC</acronym> in the document using the parameter <span class="parameter">name</span>.</div>

<div class="alert alert-info" role="alert"><strong>Note:</strong> If <b>TOCpagebreak()</b> is used at the start of a blank (<span class="smallblock">ODD</span>) page, no new page(s) will be added. This was added in mPDF 2.3 to allow a <acronym title="Table of Contents">ToC</acronym> to be placed on the first page, or to allow a <acronym title="Table of Contents">ToC</acronym> to follow another <acronym title="Table of Contents">ToC</acronym>. In this case, any properties for the continuing document are ignored. If you define several <acronym title="Table of Contents">ToC</acronym>s following immediately on from one another, set the properties in the first <acronym title="Table of Contents">ToC</acronym> you define.</div>

# Parameters

<p class="manual_block">The initial parameters specify characteristics for the <acronym title="Table of Contents">ToC</acronym>, which is generated automatically at the end of the document when <a href="{{ "/reference/mpdf-functions/output.html" | prepend: site.baseurl }}">Output()</a> is called.</p>
<p class="manual_param_dt"><span class="parameter">font </span></p>
<p class="manual_param_dd">From mPDF &gt;= 5.7 CSS styles are used to control layout of <acronym title="Table of Contents">ToC</acronym>s. Any value set for this is ignored.</p>
<p class="manual_param_dd">Set the font-family for the <acronym title="Table of Contents">ToC</acronym>.

<span class="smallblock">BLANK</span>&nbsp;or omitted uses default font-family for the document.</p>
<p><span class="parameter">font-size</span></p>
<p class="manual_param_dd">From mPDF &gt;= 5.7 CSS styles are used to control layout of <acronym title="Table of Contents">ToC</acronym>s. Any value set for this is ignored.</p>
<p class="manual_param_dd">Sets the font size for the <acronym title="Table of Contents">ToC</acronym> in <b><i>points</i></b> (pt)

<span class="smallblock">BLANK</span>&nbsp;or omitted or 0 uses the default font-size for the document.</p>
<p class="manual_param_dt"><span class="parameter">indent</span></p>
<p class="manual_param_dd">From mPDF &gt;= 5.7 CSS styles are used to control layout of <acronym title="Table of Contents">ToC</acronym>s. Any value set for this is ignored.</p>
<p class="manual_param_dd">Sets the value in millimetres to indent each level of the <acronym title="Table of Contents">ToC</acronym> from the left margin.

<span class="smallblock">BLANK</span>&nbsp;or omitted uses a default value of 5mm.</p>
<p class="manual_param_dt"><span class="parameter">paging</span> = <span class="smallblock">TRUE</span>|1|<span class="smallblock">FALSE</span>|0</p>
<p class="manual_param_dd">Specify whether to show page numbers in the <acronym title="Table of Contents">ToC</acronym>.

<span class="smallblock">BLANK</span>&nbsp;or omitted uses a default value of <span class="smallblock">TRUE</span>.

<span class="smallblock">DEFAULT</span>: <span class="smallblock">TRUE</span></p>
<p class="manual_param_dd"><b>Values</b>

<span class="smallblock">TRUE</span> <i>or</i> 1: show page numbers in the <acronym title="Table of Contents">ToC</acronym>.

<span class="smallblock">FALSE</span> <i>or</i> 0: do not show page numbers in the <acronym title="Table of Contents">ToC</acronym>.</p>
<p class="manual_param_dt"><span class="parameter">links </span> = <span class="smallblock">TRUE</span>|1|<span class="smallblock">FALSE</span>|0</p>
<p class="manual_param_dd">Specify whether to generate hyperlinks in the <acronym title="Table of Contents">ToC</acronym>.

<span class="smallblock">BLANK</span>&nbsp;or omitted uses a default value of <span class="smallblock">FALSE</span>.

<span class="smallblock">DEFAULT</span>: <span class="smallblock">FALSE</span></p>
<p class="manual_param_dd"><b>Values</b>

<span class="smallblock">TRUE</span> <i>or</i> 1: show hyperlinks in the <acronym title="Table of Contents">ToC</acronym>.

<span class="smallblock">FALSE</span> <i>or</i> 0: do not show hyperlinks in the <acronym title="Table of Contents">ToC</acronym>.</p>
<p class="manual_param_dt"><span class="parameter">toc-orientation </span></p>
<p class="manual_param_dd">This attribute specifies the orientation of the <acronym title="Table of Contents">ToC</acronym> pages.

<span class="smallblock">BLANK</span> or omitted leaves the orientation unchanged i.e. at the end of the document (before the <acronym title="Table of Contents">ToC</acronym> is generated)</p>
<p class="manual_param_dd"><b>Values</b> (case-insensitive)

L <i>or</i> landscape: Landscape

P <i>or</i> portrait:&nbsp;Portrait</p>
<p class="manual_param_dt"><span class="parameter">toc-margin-left

toc-margin-right

</span><span class="parameter">toc-margin-top

toc-margin-bottom

</span><span class="parameter">toc-margin-header

toc-margin-footer</span></p>
<p class="manual_param_dd">Set the page margins for the <acronym title="Table of Contents">ToC</acronym>. 

All values should be specified as <span class="smallblock">LENGTH</span> in millimetres.

If you are writing a <span class="smallblock">DOUBLE-SIDED</span> document, the margin values will be used for <span class="smallblock">ODD</span> pages; left and right margins will be mirrored for <span class="smallblock">EVEN</span> pages.

<span class="smallblock">BLANK</span>&nbsp;or omitted leaves the current margin unchanged i.e. the margins current at the end of the document.

"0" (zero) will set the margin to zero.</p>
<p class="manual_param_dt"><span class="parameter">toc-odd-header-name

toc-even-header-name</span><span class="parameter">

toc-odd-footer-name

</span><span class="parameter">toc-even-footer-name</span></p>
<p class="manual_param_dd">Selects a header or footer by name to use for the <acronym title="Table of Contents">ToC</acronym>. The header/footer must already have been defined using <a href="{{ "/reference/mpdf-functions/defheaderbyname.html" | prepend: site.baseurl }}">DefHeaderByName()</a>, <a href="{{ "/reference/mpdf-functions/deffooterbyname.html" | prepend: site.baseurl }}">DefFooterByName()</a>, <a href="{{ "/reference/mpdf-functions/defhtmlheaderbyname.html" | prepend: site.baseurl }}">DefHTMLHeaderByName()</a>, or <a href="{{ "/reference/mpdf-functions/defhtmlfooterbyname.html" | prepend: site.baseurl }}">DefHTMLFooterByName()</a>.

If you are writing a <span class="smallblock">SINGLE-SIDED</span> document, the values for <span class="smallblock">ODD</span> will be used for all pages, and values for <span class="smallblock">EVEN</span> will be ignored.

<span class="smallblock">BLANK</span>&nbsp;or omitted leaves the header/footer unchanged. NB <span class="smallblock">BLANK</span> will not unset the header. Set <span class="parameter">toc-</span><span class="parameter">odd-header-value</span> to -1 to turn the header off.</p>

<div class="alert alert-info" role="alert"><strong>Note:</strong> You must add the prefix 'html_' before the name if it is a HTMLHeader.</div>
<p class="manual_param_dt"><span class="parameter">toc-odd-header-value</span><span class="parameter">

toc-even-header-value

toc-odd-footer-value</span><span class="parameter">

toc-even-footer-value</span></p>
<p class="manual_param_dd">Specify whether to show a header or footer in the <acronym title="Table of Contents">ToC</acronym>. The header/footer must already have been defined using <a href="{{ "/reference/mpdf-functions/defheaderbyname.html" | prepend: site.baseurl }}">DefHeaderByName()</a>, <a href="{{ "/reference/mpdf-functions/deffooterbyname.html" | prepend: site.baseurl }}">DefFooterByName()</a>, <a href="{{ "/reference/mpdf-functions/defhtmlheaderbyname.html" | prepend: site.baseurl }}">DefHTMLHeaderByName()</a>, or <a href="{{ "/reference/mpdf-functions/defhtmlfooterbyname.html" | prepend: site.baseurl }}">DefHTMLFooterByName()</a>.

If you are writing a <span class="smallblock">SINGLE-SIDED</span> document, the values for <span class="smallblock">ODD</span> will be used for all pages, and values for <span class="smallblock">EVEN</span> will be ignored.

<span class="smallblock">BLANK</span>&nbsp;or omitted or 0 leaves the header/footer state unchanged.</p>
<p class="manual_param_dd"><b>Values</b> (case-insensitive)

1 <i>or</i> on: Show the selected header/footer in the <acronym title="Table of Contents">ToC</acronym>. 

-1 <i>or</i> off: Hide the selected header/footer in the <acronym title="Table of Contents">ToC</acronym>.</p>
<p class="manual_param_dt"><span class="parameter">toc-preHTML</span></p>
<p class="manual_param_dd">Specify the HTML code to appear before the <acronym title="Table of Contents">ToC</acronym> e.g. '&lt;h1&gt;Contents&lt;/h1&gt;'. Note that in contrast with the HTML equivalent &lt;<a href="{{ "/reference/html-control-tags/tocpagebreak.html" | prepend: site.baseurl }}">tocpagebreak</a>&gt; the text does not need to use HTML-entities.

<span class="smallblock">BLANK</span>&nbsp;or omitted will enter no text</p>
<p class="manual_param_dt"><span class="parameter">toc-postHTML</span></p>
<p class="manual_param_dd">Specify the HTML code to appear after the <acronym title="Table of Contents">ToC</acronym> e.g. '&lt;p&gt;Comments to go below the ToC&lt;/p&gt;'. Note that in contrast with the HTML equivalent &lt;<a href="{{ "/reference/html-control-tags/tocpagebreak.html" | prepend: site.baseurl }}">tocpagebreak</a>&gt; the text does not need to use HTML-entities.

<span class="smallblock">BLANK</span>&nbsp;or omitted will enter no text.</p>
<p class="manual_param_dt"><span class="parameter">toc-bookmarkText </span></p>
<p class="manual_param_dd">Specify the text as it will appear as a <span class="smallblock">BOOKMARK</span> for the <acronym title="Table of Contents">ToC</acronym>&nbsp; e.g. 'Content list'.

<span class="smallblock">BLANK</span>&nbsp;or omitted will not create a <span class="smallblock">BOOKMARK</span>.</p>
<p class="manual_param_dt"><span class="parameter">name</span></p>
<p class="manual_param_dd">Specify which <acronym title="Table of Contents">ToC</acronym> to include at this point, if using more than one <acronym title="Table of Contents">ToC</acronym> in the document. <span class="parameter">name</span> can be any alphanumeric characters (except just "0") and is case-insensitive.

<span class="smallblock">BLANK</span>&nbsp;or omitted or 0 uses the default <acronym title="Table of Contents">ToC</acronym>.</p>
<p><span class="parameter">toc-pageselector</span></p>
<p class="manual_param_dd">Select a named CSS @page for the&nbsp; <acronym title="Table of Contents">ToC</acronym>.

<span class="smallblock">BLANK</span>&nbsp;or omitted or leaves the CSS page unchanged.</p>
<p class="manual_param_dd">See <a href="{{ "/paging/using-page.html" | prepend: site.baseurl }}">Using @page</a> for more information</p>
<p class="manual_param_dt"><span class="parameter">toc-sheet-size</span></p>
<p class="manual_param_dd"><span class="parameter">sheet-size</span> can be specified either as a pre-defined page size, or as an array of width and height in millimetres e.g. array(210,297).

<span class="smallblock">DEFAULT</span>: <span class="smallblock">BLANK</span> - makes no change to the current sheet-size</p>
<p class="manual_param_dd"><b>Values</b> (case-insensitive)

A0 - A10, B0 - B10, C0 - C10

4A0, 2A0, RA0 - RA4, SRA0 - SRA4

Letter, Legal, Executive, Folio

Demy, Royal

A (Type A paperback 111x178mm)

B (Type B paperback 128x198mm)</p>
<p class="manual_param_dd">All of the above values can be suffixed with "-L" to force a Landscape page orientation document e.g. "A4-L"</p>
<p><span class="parameter">outdent</span></p>
<p class="manual_param_dd">Set a negative indent for the last line of each <acronym title="Table of Contents">ToC</acronym> entry.

Values should be <span class="smallblock">BLANK </span>string or any valid CSS <span class="smallblock">LENGTH</span>.

This will cause the line to extend beyond the right margin; you can prevent this by setting <span class="smallblock">PADDING-RIGHT</span> equal to this value.

<span class="smallblock">DEFAULT</span> 0</p>
<p class="manual_param_dt"><span class="parameter">toc-resetpagenum</span> = 1 - ∞</p>
<p class="manual_param_dd">Sets/resets the document page number to <span class="parameter">resetpagenum</span> starting on the <acronym title="Table of Contents">ToC</acronym>. (The value must be a positive integer).

<span class="smallblock">BLANK</span>&nbsp;or omitted or 0 leaves the preceding page number sequence&nbsp;unchanged.</p>
<p class="manual_param_dt"><span class="parameter">toc-pagenumstyle</span> = 1|A|a|I|i|[+ any value supported for list-style-type]</p>
<p class="manual_param_dd">Sets/resets the page numbering style to use in the <acronym title="Table of Contents">ToC</acronym> (values as for cf. <a href="{{ "/css-stylesheets/supported-css.html" | prepend: site.baseurl }}">lists</a>)

<span class="smallblock">BLANK</span>&nbsp;or omitted leaves the current&nbsp;page number&nbsp;style&nbsp;unchanged.</p>
<p class="manual_param_dd"><b>Values</b> (case-sensitive)

1: Decimal - 1,2,3,4...

A: Alpha uppercase - A,B,C,D...

a: Alpha lowercase - a,b,c,d...

I: Roman uppercase - I, II, III, IV...

i: Roman lowercase - i, ii, iii, iv...</p>
<p class="manual_param_dt"><span class="parameter">toc-suppress</span> = <span class="smallblock">TRUE</span>|<span class="smallblock">FALSE</span>|1|0</p>
<p class="manual_param_dd"><span class="parameter">suppress</span>=on will suppress document page numbers in the <acronym title="Table of Contents">ToC</acronym> 

<span class="smallblock">BLANK</span>&nbsp;or omitted leaves the current&nbsp;condition unchanged.</p>
<p class="manual_param_dd"><b>Values</b> (case-insensitive)

1 <i>or</i> <span class="smallblock">TRUE</span>: Suppress (hide) page numbers in the <acronym title="Table of Contents">ToC</acronym>

0 <i>or</i> <span class="smallblock">FALSE</span>: Show page numbers in the <acronym title="Table of Contents">ToC</acronym></p>
<p class="manual_block">The rest of the parameters are defined exactly as for <a href="{{ "/reference/mpdf-functions/addpage.html" | prepend: site.baseurl }}">AddPage()</a>. Note that these parameters define page numbering, margins, headers/footers for the document as it continues from this point on; in the final document this will be the part of the document immediately after the <acronym title="Table of Contents">ToC</acronym>.

Please refer to <a href="{{ "/reference/mpdf-functions/addpage.html" | prepend: site.baseurl }}">AddPage()</a> for further details. But <b>note</b> there are differences in the order of the parameters especially take care with <span class="parameter">$orientation</span></p>

# Changelog

<table class="table"> <thead>
<tr> <th>Version</th><th>Description</th> </tr>
</thead> <tbody>
<tr>
<td>2.0</td>
<td>
<p>Function was added.</p>
</td>
</tr>
<tr>
<td>2.2</td>
<td>Default values for <span class="parameter">font-size</span>, <span class="parameter">paging</span> and <span class="parameter">links</span> were redefined.</td>
</tr>
<tr>
<td>2.3</td>
<td><span class="parameter">name</span> attribute was added.</td>
</tr>
<tr>
<td>4.3</td>
<td>
<p>Parameters <span class="parameter">pageselector</span>, <span class="parameter">sheet-size</span>,</p>
<p><span class="parameter">toc-pageselector</span> and <span class="parameter">toc-sheet-size</span> were added</p>
</td>
</tr>
<tr>
<td>5.7</td>
<td>
<p><span class="parameter">outdent</span> parameter added</p>
<p><span class="parameter">font</span>, <span class="parameter">font-size</span> and <span class="parameter">indent</span> redundant</p>
</td>
</tr>
<tr>
<td>6.0</td>
<td>Parameters added:&nbsp; <span class="parameter">toc-resetpagenum</span> | <span class="parameter">toc-pagenumstyle</span> | <span class="parameter">toc-suppress</span></td>
</tr>
</tbody> </table>

# Examples

{% highlight php %}
Example #1
{% endhighlight %}

{% highlight php %}
<?php

<?php

$mpdf=new mPDF();

$mpdf->WriteHTML('Introduction');

$mpdf->TOCpagebreak();

$mpdf->TOC_Entry("Chapter 1",0);

$mpdf->WriteHTML('Chapter 1 ...');

$mpdf=Output();

?>
{% endhighlight %}

# See Also

<ul>
<li class="manual_boxlist"><a href="{{ "/reference/mpdf-functions/toc-entry.html" | prepend: site.baseurl }}">TOC_Entry()</a> - Add an entry for Table of Contents</li>
<li class="manual_boxlist"><a href="{{ "/reference/mpdf-functions/addpage.html" | prepend: site.baseurl }}">AddPage()</a> - Add a new page</li>
<li class="manual_boxlist">&lt;<a href="{{ "/reference/html-control-tags/tocpagebreak.html" | prepend: site.baseurl }}">tocpagebreak</a>&gt; - Custom HTML tag - equivalent to <b>TOCpagebreak()</b></li>
</ul>