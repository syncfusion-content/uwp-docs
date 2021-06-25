---
layout: post
title: Customizing progress ring in UWP PDF Viewer control | Syncfusion
description: Learn here all about Customizing progress ring support in Syncfusion UWP PDF Viewer (SfPdfViewer) control and more.
platform: uwp
control: PDF viewer
documentation: ug
---

# Customizing progress ring in UWP PDF Viewer (SfPdfViewer)
The following code illustrates the design of the progress ring in red color foreground with dimension of 100x100. Here 'buffer' is the byte array read from the PDF file either using FileOpenPicker or from Assets folder, as illustrated in the [Viewing PDF](https://help.syncfusion.com/uwp/sfpdfviewer/concepts-and-features/viewing-pdf) section. 
{% tabs %}
{% highlight c# %}
PdfLoadedDocument loadedDocument = new PdfLoadedDocument(buffer);
pdfViewer.LoadDocument(loadedDocument);
//Creates custom progress ring.
ProgressRing progressRing = new ProgressRing();
progressRing.Foreground = new SolidColorBrush(Windows.UI.Color.FromArgb(255, 255, 0, 0));
progressRing.Width = 100;
progressRing.Height = 100;
//Assigns custom progress ring to the Viewer control.
pdfViewer.PdfProgressRing = progressRing;
{% endhighlight %}
{% highlight vbnet %}
Dim loadedDocument As New PdfLoadedDocument(Buffer)
pdfViewer.LoadDocument(loadedDocument)
'Creates custom progress ring.
Dim progressRing As New ProgressRing()
progressRing.Foreground = New SolidColorBrush(Windows.UI.Color.FromArgb(255, 255, 0, 0))
progressRing.Width = 100
progressRing.Height = 100
'Assigns custom progress ring to the Viewer control.
pdfViewer.PdfProgressRing = progressRing
{% endhighlight %}
{% endtabs %}
