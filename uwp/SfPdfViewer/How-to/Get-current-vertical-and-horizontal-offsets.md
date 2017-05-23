---
layout: post
title: Get current vertical and horizontal offsets of Syncfusion Essential UWP PDF viewer.
description: Get current vertical and horizontal offsets of Syncfusion Essential UWP PDF viewer.
platform: uwp
control: PDF viewer
documentation: ug
---

## Get current vertical and horizontal offsets
The SfPdfViewer control provides the value of the current vertical and horizontal offsets. The following code allows you to access the same.
{% tabs %}
{% highlight c# %}
PdfLoadedDocument loadedDocument = new PdfLoadedDocument(buffer);
pdfViewer.LoadDocument(loadedDocument);
//Gets Vertical Offset of a document.
float vOffset = pdfViewer.VerticalOffset;
//Gets Horizontal Offset of a document.
float hOffset = pdfViewer.HorizontalOffset;
{% endhighlight %}
{% highlight vbnet %}
Dim loadedDocument As New PdfLoadedDocument(Buffer)
pdfViewer.LoadDocument(loadedDocument)
'Gets Vertical Offset of a document.
Dim vOffset As Single = pdfViewer.VerticalOffset
'Gets Horizontal Offset of a document.
Dim hOffset As Single = pdfViewer.HorizontalOffset
{% endhighlight %}
{% endtabs %}