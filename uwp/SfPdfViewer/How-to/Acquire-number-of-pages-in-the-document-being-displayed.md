---
layout: post
title: Acquire number of pages in the document being displayed in Syncfusion Essential UWP PDF viewer.
description: Acquire number of pages in the document being displayed in Syncfusion Essential UWP PDF viewer.
platform: uwp
control: PDF viewer
documentation: ug
---

## Acquire number of pages in the document being displayed
The following code can be used to access the total number of pages displayed in the PDF Viewer.
{% tabs %}
{% highlight c# %}
PdfLoadedDocument ldoc = new PdfLoadedDocument(buffer);
pdfViewer.LoadDocument(ldoc);
//Gets the total page count. 
int pageCount = pdfViewer.PageCount;
{% endhighlight %}
{% highlight vbnet %}
Dim ldoc As New PdfLoadedDocument(Buffer)
pdfViewer.LoadDocument(ldoc)
'Gets the total page count. 
Dim pageCount As Integer = pdfViewer.PageCount
{% endhighlight %}
{% endtabs %}