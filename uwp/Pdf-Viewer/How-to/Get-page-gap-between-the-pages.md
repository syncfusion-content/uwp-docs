---
layout: post
title: Get page gap between the pages in Syncfusion Essential UWP PDF viewer.
description: Get page gap between the pages in Syncfusion Essential UWP PDF viewer.
platform: uwp
control: PDF viewer
documentation: ug
---

## Get page gap between the pages
The SfPdfViewer control provides the property to access the gap between two pages being displayed in the PDF Viewer. This value can be accessed using the following code. Here 'buffer' is the byte array read from the PDF file either using FileOpenPicker or from Assets folder, as illustrated in the [Viewing PDF](https://help.syncfusion.com/uwp/sfpdfviewer/concepts-and-features/viewing-pdf) section.
{% tabs %}
{% highlight c# %}
PdfLoadedDocument loadedDocument = new PdfLoadedDocument(buffer);
pdfViewer.LoadDocument(loadedDocument);
//Gets the gap between two pages.
int pageGap = pdfViewer.PageGap;
{% endhighlight %}
{% highlight vbnet %}
Dim loadedDocument As New PdfLoadedDocument(Buffer)
pdfViewer.LoadDocument(loadedDocument)
'Gets the gap between two pages.
Dim pageGap As Integer = pdfViewer.PageGap
{% endhighlight %}
{% endtabs %}
