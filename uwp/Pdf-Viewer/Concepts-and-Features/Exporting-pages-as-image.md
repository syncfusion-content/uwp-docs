---
layout: post
title: Exporting pages as images in UWP Pdf Viewer control | Syncfusion
description: Learn here all about Exporting pages as images support in Syncfusion UWP Pdf Viewer (SfPdfViewer) control and more.
platform: uwp
control: PDF viewer
documentation: ug
---

# Exporting pages as images in UWP Pdf Viewer (SfPdfViewer)

The SfPdfViewer allow user to export page of the PDF document as an Image. Here 'buffer' is the byte array read from the PDF file either using FileOpenPicker or from Assets folder, as illustrated in the [Viewing PDF](https://help.syncfusion.com/uwp/sfpdfviewer/concepts-and-features/viewing-pdf) section. 

{% tabs %}
{% highlight c# %}
PdfLoadedDocument loadedDocument = new PdfLoadedDocument(buffer);
pdfViewer.LoadDocument(loadedDocument);
//Exports the second page of the PDF document as an Image.
Image pageImg = pdfViewer.GetPage(2);
{% endhighlight %}
{% highlight vbnet %}
Dim loadedDocument As New PdfLoadedDocument(Buffer)
pdfViewer.LoadDocument(loadedDocument)
'Exports the second page of the PDF document as an Image.
Dim pageImg As Image = pdfViewer.GetPage(2)
{% endhighlight %}
{% endtabs %}

To export a single page of the PDF document as an Image with custom zoom factor, use the below code.

{% tabs %}
{% highlight c# %}
PdfLoadedDocument loadedDocument = new PdfLoadedDocument(buffer);
pdfViewer.LoadDocument(loadedDocument);
//Exports the second page of the PDF document as an Image 300% magnified.
Image pageImg = pdfViewer.GetPage(2, 300);
{% endhighlight %}
{% highlight vbnet %}
Dim loadedDocument As New PdfLoadedDocument(Buffer)
pdfViewer.LoadDocument(loadedDocument)
'Exports the second page of the PDF document as an Image 300% magnified.
Dim pageImg As Image = pdfViewer.GetPage(2, 300)
{% endhighlight %}
{% endtabs %}

The following code explains how to export multiple pages as images.

{% tabs %}
{% highlight c# %}
PdfLoadedDocument loadedDocument = new PdfLoadedDocument(buffer);
pdfViewer.LoadDocument(loadedDocument);
//Exports the pages between start and end page index as image array.
Image[] pageImgCollection = pdfViewer.GetPages(0, 5);
{% endhighlight %}
{% highlight vbnet %}
Dim loadedDocument As New PdfLoadedDocument(Buffer)
pdfViewer.LoadDocument(loadedDocument)
'Exports the pages between start and end page index as image array.
Dim pageImgCollection As Image() = pdfViewer.GetPages(0, 5)
{% endhighlight %}
{% endtabs %}

To export multiple pages as images with custom magnification factor, please follow the below code.

{% tabs %}
{% highlight c# %}
PdfLoadedDocument loadedDocument = new PdfLoadedDocument(buffer);
pdfViewer.LoadDocument(loadedDocument);
//Exports the pages between start and end index as image array in the mentioned zoom factor.
Image[] pageImgCollection = pdfViewer.GetPages(0, 5, 200);
{% endhighlight %}
{% highlight vbnet %}
Dim loadedDocument As New PdfLoadedDocument(Buffer)
pdfViewer.LoadDocument(loadedDocument)
'Exports the pages between start and end index as image array in the mentioned zoom factor.
Dim pageImgCollection As Image() = pdfViewer.GetPage(0, 5, 200)
{% endhighlight %}
{% endtabs %}

The SfPdfViewer allows the user to export pages of the PDF document as image stream to save the image in the disk.

{% tabs %}
{% highlight c# %}
PdfLoadedDocument loadedDocument = new PdfLoadedDocument(buffer);
pdfViewer.LoadDocument(loadedDocument);
//Exports the second page of the PDF document as an Image.
Stream imageStream = pdfViewer.ExportAsImage(2);
{% endhighlight %}
{% highlight vbnet %}
Dim loadedDocument As New PdfLoadedDocument(Buffer)
pdfViewer.LoadDocument(loadedDocument)
'Exports the second page of the PDF document as an Image.
Dim imageStream As Stream = pdfViewer.ExportAsImage(2)
{% endhighlight %}
{% endtabs %}

To export page of PDF document as image stream with customized zoom factor, use the below code.

{% tabs %}
{% highlight c# %}
PdfLoadedDocument loadedDocument = new PdfLoadedDocument(buffer);
pdfViewer.LoadDocument(loadedDocument);
//Exports the second page of the PDF document as an Image 300% magnified.
Stream imageStream = pdfViewer.ExportAsImage(2, 300);
{% endhighlight %}
{% highlight vbnet %}
Dim loadedDocument As New PdfLoadedDocument(Buffer)
pdfViewer.LoadDocument(loadedDocument)
'Exports the second page of the PDF document as an Image 300% magnified.
Dim imageStream As Stream = pdfViewer.ExportAsImage(2, 300)
{% endhighlight %}
{% endtabs %}

To export pages of PDF document as List of image streams, use the below code.

{% tabs %}
{% highlight c# %}
PdfLoadedDocument loadedDocument = new PdfLoadedDocument(buffer);
pdfViewer.LoadDocument(loadedDocument);
//Exports the pages between start and end index as image array.
List<Stream> listOfImageStream = pdfViewer.ExportAsImage(0, 5);
{% endhighlight %}
{% highlight vbnet %}
Dim loadedDocument As New PdfLoadedDocument(Buffer)
pdfViewer.LoadDocument(loadedDocument)
'Exports the pages between start and end index as image array.
Dim listOfImageStream As List(Of Stream) = pdfViewer.ExportAsImage(0, 5)
{% endhighlight %}
{% endtabs %}

To export pages of PDF document as list of image streams with custom zoom factor follow the below code.

{% tabs %}
{% highlight c# %}
PdfLoadedDocument loadedDocument = new PdfLoadedDocument(buffer);
pdfViewer.LoadDocument(loadedDocument);
//Exports the pages between start and end index as image array. 
List<Stream> listOfImageStream = pdfViewer.ExportAsImage(0, 5, 200);
{% endhighlight %}
{% highlight vbnet %}
Dim loadedDocument As New PdfLoadedDocument(Buffer)
pdfViewer.LoadDocument(loadedDocument)
'Exports the pages between start and end index as image array.
Dim listOfImageStream As List(Of Stream) = pdfViewer.ExportAsImage(0, 5, 200)
{% endhighlight %}
{% endtabs %}
