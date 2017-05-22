---
layout: post
title: Toggle the display of the page number in Syncfusion Essential UWP PDF viewer.
description: Toggle the display of the page number in Syncfusion Essential UWP PDF viewer.
platform: uwp
control: PDF viewer
documentation: ug
---

## Toggle the display of the page number
The following code example can be used to disable the display of the page number on the top left corner of each page. 
{% tabs %}
{% highlight c# %}
PdfLoadedDocument loadedDocument = new PdfLoadedDocument(buffer);
pdfViewer.LoadDocument(loadedDocument);
//Disables the display of the page number.
pdfViewer.ShowPageNumber = false;
{% endhighlight %}
{% highlight vbnet %}
Dim loadedDocument As New PdfLoadedDocument(Buffer)
pdfViewer.LoadDocument(loadedDocument)
'Disables the display of the page number.
pdfViewer.ShowPageNumber = False
{% endhighlight %}
{% endtabs %}
