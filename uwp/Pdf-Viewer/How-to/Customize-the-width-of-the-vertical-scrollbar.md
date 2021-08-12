---
layout: post
title: Toggle the display of the page number in UWP PDF viewer | Syncfusion
description: Learn here about Toggle the display of the page number support in UWP PDF viewer control and disable the display of the page number, and more.
platform: uwp
control: PDF viewer
documentation: ug
---

# Customize the width of the vertical scrollbar

The PDF viewer uses the [ScrollViewer](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.controls.scrollviewer?view=winrt-20348) control to scroll the pages of the PDF. The width of the vertical scrollbar of the [ScrollViewer](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.controls.scrollviewer?view=winrt-20348) can be modified by using the [VerticalScrollBarWidth](https://help.syncfusion.com/cr/uwp/Syncfusion.Windows.PdfViewer.SfPdfViewerControl.html#Syncfusion_Windows_PdfViewer_SfPdfViewerControl_VerticalScrollBarWidth) property. The default value of the API is as same as the default width of the vertical scrollbar of the [ScrollViewer](https://docs.microsoft.com/en-us/uwp/api/windows.ui.xaml.controls.scrollviewer?view=winrt-20348) control.

{% tabs %}
{% highlight c# %}

//Sets the width of the vertical scrollbar in the PDF Viewer. 
pdfViewerControl.VerticalScrollBarWidth = 100; 
//Gets the width of the vertical scrollbar in the PDF Viewer. 
double verticalScrollBarWidth = pdfViewerControl.VerticalScrollBarWidth;

{% endhighlight %}
{% endtabs %}
