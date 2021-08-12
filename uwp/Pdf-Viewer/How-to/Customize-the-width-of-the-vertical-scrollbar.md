---
layout: post
title: Toggle the display of the page number in UWP PDF viewer | Syncfusion
description: Learn here about Toggle the display of the page number support in UWP PDF viewer control and disable the display of the page number, and more.
platform: uwp
control: PDF viewer
documentation: ug
---

# Customize the width of the vertical scrollbar

The PDF viewer uses the `ScrollViewer` control to scroll the pages of the PDF. The width of the vertical scrollbar of the `ScrollViewer` can be modified by using the `VerticalScrollBarWidth` property. The default value of the API is as same as the default width of the vertical scrollbar of the `ScrollViewer` control. 

{% tabs %}
{% highlight c# %}

//Sets the width of the vertical scrollbar in the PDF Viewer. 
pdfViewerControl.VerticalScrollBarWidth = 100; 
//Gets the width of the vertical scrollbar in the PDF Viewer. 
double verticalScrollBarWidth = pdfViewerControl.VerticalScrollBarWidth;

{% endhighlight %}
{% endtabs %}
