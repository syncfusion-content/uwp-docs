---
layout: post
title: Check the document is edited or not in Syncfusion UWP PDF Viewer
description: Check whether the loaded PDF document is edited or not in Syncfusion Essential<sup>®</sup> UWP PDF viewer control.
platform: uwp
control: PDF viewer
documentation: ug
---

# How to check whether the loaded PDF document is edited or not?
The [`IsDocumentEdited`](https://help.syncfusion.com/cr/uwp/Syncfusion.Windows.PdfViewer.SfPdfViewerControl.html#Syncfusion_Windows_PdfViewer_SfPdfViewerControl_IsDocumentEdited) property is a bindable property that returns a value that indicates whether the PDF is edited or not. 

This property will be `true` when any annotations or form fields values are changed in the loaded PDF document. It will be reset to `false` when the PDF is saved. The undo and redo operations that change the annotations or form fields from their respective states at the time of saving will also set this property to `true`.

Refer to the following code example.

{% tabs %}
{% highlight xaml %}
//Retreives the value indicating whether the PDF document is edited
 <Grid Loaded="Grid_Loaded">    
    <syncfusion:SfPdfViewerControl Grid.Row="1" x:Name="pdfViewer" IsDocumentEdited="{Binding DocumentEdited}" />
 </Grid>
{% endhighlight %}
{% endtabs %}

N> The default value is `false`.