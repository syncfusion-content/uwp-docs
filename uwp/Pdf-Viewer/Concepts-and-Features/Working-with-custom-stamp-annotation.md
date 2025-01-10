---
layout: post
title: Custom stamp annotation in UWP PDF Viewer control | Syncfusion
description: Learn about Custom stamp annotation support in Syncfusion<sup>®</sup> UWP PDF Viewer (SfPdfViewer) control and more.
platform: uwp
control: SfPdfViewerControl
documentation: ug
---

# Working with custom stamp annotations in UWP PDF Viewer (SfPdfViewer)

The PDF Viewer allows you to include any form of UIElement (Button, Entry, Label, Image, and more) anywhere in the pages of the PDF Viewer as a custom stamp annotation. You can add, move, resize, and delete the custom stamp annotations. Also, you can save and load the existing custom stamp annotation associated with a PDF document.

N> Stamp annotations can be saved only by using the SaveAsync method.

## Add a custom stamp

The custom stamps can be added using the [`AddStamp`](https://help.syncfusion.com/cr/uwp/Syncfusion.Windows.PdfViewer.SfPdfViewerControl.html#Syncfusion_Windows_PdfViewer_SfPdfViewerControl_AddStamp_Windows_UI_Xaml_UIElement_System_Int32_) method.

<table>

<tr>
<th>Method</th>
<th>Action</th>
</tr>

<tr>
<td>AddStamp(view, pageNumber)</td>
<td>Add custom stamp to the specified page.</td>
</tr>

<tr>
<td>AddStamp(view, pageNumber, position)</td>
<td>Add custom stamp to the specified page and position as Point object.</td>
</tr>

<tr>
<td>AddStamp(view, pageNumber, bounds)</td>
<td>Add custom stamp to the specified page and position as Rectangle object.</td>
</tr>

</table>

A typical example of a custom stamp in the real world includes adding an image as a custom stamp. The PDF Viewer provides an option to add any user-defined signature or seal image as a custom stamp to a PDF document. The following code sample explains the same.

{% tabs %}
{% highlight c# %}

private async void Button_Clicked(object sender, RoutedEventArgs e)
{
    //Set the image source.
    Image image = new Image();
    Stream imageStream = typeof(MainPage).GetTypeInfo().Assembly.GetManifestResourceStream("PdfViewerCustomToolbar.Assets.Image.png");
    StackPanel grid = new StackPanel();
    grid.Height = 100; 
    grid.Width = 100; 
    BitmapImage bitmap = new BitmapImage();
    bitmap.DecodePixelHeight = 500;
    bitmap.DecodePixelWidth = 500;
    await bitmap.SetSourceAsync(imageStream.AsRandomAccessStream());
    image.Source = bitmap;
    if (image.Source != null)
        grid.Children.Add(image);
    //Add the image as a custom stamp to the first page using the AddStamp method.
    pdfViewer.AddStamp(grid, 1, new Point(100,100));
}

{% endhighlight %}
{% endtabs %}