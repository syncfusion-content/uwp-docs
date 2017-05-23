---
layout: post
title: Disable thumbnail view in Syncfusion Essential UWP PDF viewer.
description: Disable thumbnail view in Syncfusion Essential UWP PDF viewer.
platform: uwp
control: PDF viewer
documentation: ug
---

## Disable thumbnail view
The SfPdfViewer control allows you to enable and disable thumbnail view that is opened when the document is magnified below 100%. The following code illustrates the same.
{% tabs %}
{% highlight c# %}
PdfLoadedDocument loadedDocument = new PdfLoadedDocument(buffer);
pdfViewer.LoadDocument(loadedDocument);
//Disables Thumbnail View.
pdfViewer.IsThumbnailViewEnabled = false;
{% endhighlight %}
{% highlight vbnet %}
Dim loadedDocument As New PdfLoadedDocument(Buffer)
pdfViewer.LoadDocument(loadedDocument)
'Disables Thumbnail View.
pdfViewer.IsThumbnailViewEnabled = False
{% endhighlight %}
{% endtabs %}
