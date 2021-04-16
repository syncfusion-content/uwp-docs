---
layout: post
title: Acquire number of pages in the document being displayed in Syncfusion Essential UWP PDF viewer.
description: Acquire number of pages in the document being displayed in Syncfusion Essential UWP PDF viewer.
platform: uwp
control: PDF viewer
documentation: ug
---

## Acquire number of pages in the document being displayed
The following code can be used to access the total number of pages displayed in the [PDF Viewer](https://help.syncfusion.com/cr/uwp/Syncfusion.Windows.PdfViewer.SfPdfViewerControl.html). Here 'buffer' is the byte array read from the PDF file either using FileOpenPicker or from Assets folder, as illustrated in the [Viewing PDF](https://help.syncfusion.com/uwp/sfpdfviewer/concepts-and-features/viewing-pdf) section.
{% tabs %}
{% highlight c# %}

using Syncfusion.Windows.PdfViewer;

PdfLoadedDocument loadedDocument = new PdfLoadedDocument(buffer);
pdfViewer.LoadDocument(loadedDocument);
//Gets the total page count. 
int pageCount = pdfViewer.PageCount;
{% endhighlight %}
{% highlight vbnet %}
Dim loadedDocument As New PdfLoadedDocument(Buffer)
pdfViewer.LoadDocument(loadedDocument)
'Gets the total page count. 
Dim pageCount As Integer = pdfViewer.PageCount
{% endhighlight %}
{% endtabs %}