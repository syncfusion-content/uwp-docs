---
layout: post
title: Get current vertical and horizontal offsets of Syncfusion Essential UWP PDF viewer.
description: Get current vertical and horizontal offsets of Syncfusion Essential UWP PDF viewer.
platform: uwp
control: PDF viewer
documentation: ug
---

# Get current vertical and horizontal offsets in UWP PDF Viewer
The SfPdfViewer control provides the value of the current vertical and horizontal offsets. The following code allows you to access the same. Here 'buffer' is the byte array read from the PDF file either using FileOpenPicker or from Assets folder, as illustrated in the [Viewing PDF](https://help.syncfusion.com/uwp/sfpdfviewer/concepts-and-features/viewing-pdf) section. 
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