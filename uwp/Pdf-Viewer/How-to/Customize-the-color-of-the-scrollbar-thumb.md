---
layout: post
title: Customize the color of the scrollbar thumb | Syncfusion
description: The Syncfusion Essential UWP PDF viewer provides option to customize the color of the scrollbar thumb.
platform: uwp
control: PDF viewer
documentation: ug
---

## Customize the color of the scrollbar thumb

The PDF viewer uses the `ScrollViewer` control to scroll the pages of a PDF. The color of the vertical and horizontal scrollbar thumbs can be customized using the following code. 
 
{% tabs %}
{% highlight xaml %}
<sf:SfPdfViewerControl x:Name = “pdfViewer”>
<sf:SfPdfViewerControl.Resources>
        <SolidColorBrush x:Key="ScrollBarThumbFill" Color="Gold"/>
        <SolidColorBrush x:Key="ScrollBarThumbFillPointerOver" Color="Orange"/>
        <SolidColorBrush x:Key="ScrollBarThumbFillPressed" Color="Red"/>
        <SolidColorBrush x:Key="ScrollBarThumbFillDisabled" Color="Pink"/>
</sf:SfPdfViewerControl.Resources>
</sf:SfPdfViewerControl>
{% endhighlight %}
{% endtabs %}
