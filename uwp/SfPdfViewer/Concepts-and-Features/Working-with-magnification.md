---
layout: post
title: Working with magnification in Syncfusion Essential UWP PDF viewer.
description: Working with magnification in Syncfusion Essential UWP PDF viewer.
platform: uwp
control: PDF viewer
documentation: ug
---

## Working with magnification

Magnification of the PDF document can be done in multiple ways and the different ways are explained below. By default the viewer control supports ctrl+ mouse scroll to manipulate the magnification of the document. 

**Setting Custom zoom**

The user is allowed to set custom magnification factor between 100 and 300 to magnify the document displayed. The following code illustrates the same.

{% tabs %}
{% highlight c# %}
PdfLoadedDocument loadedDocument = new PdfLoadedDocument(buffer);
pdfViewer.LoadDocument(loadedDocument);
//Sets magnification value to 140%.
pdfViewer.ZoomTo(140);
{% endhighlight %}
{% highlight vbnet %}
Dim loadedDocument As New PdfLoadedDocument(Buffer)
pdfViewer.LoadDocument(loadedDocument)
'Sets magnification value to 140%.
pdfViewer.ZoomTo(140)
{% endhighlight %}
{% endtabs %}

**Getting current zoom factor**

The following code illustrates accessing zoom factor in which the document is displayed in the viewer.

{% tabs %}
{% highlight c# %}
PdfLoadedDocument loadedDocument = new PdfLoadedDocument(buffer);
pdfViewer.LoadDocument(loadedDocument);
//Gets the current zoom value of PDF Viewer
int zoom = pdfViewer.Zoom;
{% endhighlight %}
{% highlight vbnet %}
Dim loadedDocument As New PdfLoadedDocument(Buffer)
pdfViewer.LoadDocument(loadedDocument)
'Gets the current zoom value of PDF Viewer
Dim zoom As Integer = pdfViewer.Zoom
{% endhighlight %}
{% endtabs %}

**Working with View Modes**

The SfPdfViewerControl supports the below three view modes for better viewing experience.

* FitWidth
* Normal
* OnePage

The below code explains how to set the view mode to FitWidth.

{% tabs %}
{% highlight c# %}
PdfLoadedDocument loadedDocument = new PdfLoadedDocument(buffer);
pdfViewer.LoadDocument(loadedDocument);
// Sets the PDF Page View Mode to Fit Width. 
pdfViewer.ViewMode = PageViewMode.FitWidth;
{% endhighlight %}
{% highlight vbnet %}
Dim loadedDocument As New PdfLoadedDocument(Buffer)
pdfViewer.LoadDocument(loadedDocument)
'Sets the PDF Page View Mode to Fit Width. 
pdfViewer.ViewMode = PageViewMode.FitWidth
{% endhighlight %}
{% endtabs %}

The below code explains how to set the view mode to Normal.

{% tabs %}
{% highlight c# %}
PdfLoadedDocument loadedDocument = new PdfLoadedDocument(buffer);
pdfViewer.LoadDocument(loadedDocument);
// Sets the PDF Page View Mode to Normal. 
pdfViewer.ViewMode = PageViewMode.Normal;
{% endhighlight %}
{% highlight vbnet %}
Dim loadedDocument As New PdfLoadedDocument(Buffer)
pdfViewer.LoadDocument(loadedDocument)
'Sets the PDF Page View Mode to Normal. 
pdfViewer.ViewMode = PageViewMode.Normal
{% endhighlight %}
{% endtabs %}
The below code explains how to set the view mode to OnePage.
{% tabs %}
{% highlight c# %}
PdfLoadedDocument loadedDocument = new PdfLoadedDocument(buffer);
pdfViewer.LoadDocument(loadedDocument);
// Sets the PDF Page View Mode to Single Page View.
pdfViewer.ViewMode = PageViewMode.OnePage;
{% endhighlight %}
{% highlight vbnet %}
Dim loadedDocument As New PdfLoadedDocument(Buffer)
pdfViewer.LoadDocument(loadedDocument)
'Sets the PDF Page View Mode to Single Page View.
pdfViewer.ViewMode = PageViewMode.OnePage
{% endhighlight %}
{% endtabs %}

N> 
* In Desktop view, when the zoom value is reduced below 100 percentage, the view will be automatically changes to show the thumbnails for easier navigation.
* One page view mode is supported only in mobile view, where the view will be changed to Flip View for easier navigation.
