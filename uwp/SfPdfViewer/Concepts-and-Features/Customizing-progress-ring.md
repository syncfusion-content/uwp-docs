---
layout: post
title: Customizing progress ring in Syncfusion Essential UWP PDF viewer.
description: Customizing progress ring in Syncfusion Essential UWP PDF viewer.
platform: uwp
control: PDF viewer
documentation: ug
---

## Customizing progress ring
The following code illustrates the design of the progress ring in red color foreground with dimension of 100x100.
{% tabs %}
{% highlight c# %}
PdfLoadedDocument ldoc = new PdfLoadedDocument(buffer);
pdfViewer.LoadDocument(ldoc);
//Creates custom progress ring.
ProgressRing progressRing = new ProgressRing();
progressRing.Foreground = new SolidColorBrush(Windows.UI.Color.FromArgb(255, 255, 0, 0));
progressRing.Width = 100;
progressRing.Height = 100;
//Assigns custom progress ring to the Viewer control.
pdfViewer.PdfProgressRing = progressRing;
{% endhighlight %}
{% highlight vbnet %}
Dim ldoc As New PdfLoadedDocument(Buffer)
pdfViewer.LoadDocument(ldoc)
'Creates custom progress ring.
Dim progressRing As New ProgressRing()
progressRing.Foreground = New SolidColorBrush(Windows.UI.Color.FromArgb(255, 255, 0, 0))
progressRing.Width = 100
progressRing.Height = 100
'Assigns custom progress ring to the Viewer control.
pdfViewer.PdfProgressRing = progressRing
{% endhighlight %}
{% endtabs %}