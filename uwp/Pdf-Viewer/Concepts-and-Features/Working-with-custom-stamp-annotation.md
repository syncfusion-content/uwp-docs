---
layout: post
title: Custom stamp annotation in UWP PDF Viewer control | Syncfusion
description: Learn here all about Custom stamp annotation support in Syncfusion UWP PDF Viewer (SfPdfViewer) control and more.
platform: UWP
control: SfPdfViewerControl
documentation: ug
---

# Working with custom stamp annotations in UWP PDF Viewer (SfPdfViewer)

PDFViewer allows you to include any form of UIElement (Button, Entry, Label, Image, etc.) anywhere in the pages of the PDF Viewer as a custom stamp annotation. You can perform operations like add, move, resize, and delete the custom stamp annotations. Also, you can save and load the existing custom stamp annotation that is associated with the PDF document.

N> Stamp annotations can be saved only by using the SaveAsync method.

## Add a custom stamp

The custom stamps can be added using the `AddStamp` methods.

{% tabs %}
{% highlight c# %}

//Add custom stamp to the specified page
pdfViewer.AddStamp(UIElement view, int pageNumber)
//Add custom stamp to the specified page and position as Point object
pdfViewer.AddStamp(UIElement view, int pageNumber, Point position)
//Add custom stamp to the specified page and position as Rectangle object
pdfViewer.AddStamp(UIElement view, int pageNumber, Rect bounds)

{% endhighlight %}
{% endtabs %}

A typical example of the custom stamp in the real world includes, adding an image as custom stamp. PDF Viewer provides option to add any user defined signature or seal image as custom stamp to the PDF document. The following code sample explains the same.

{% tabs %}
{% highlight c# %}

private async void Button_Clicked(object sender, RoutedEventArgs e)
{
    //Set image source
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
    //Add image as custom stamp to the first page using `AddStamp` method
    pdfViewer.AddStamp(grid, 1, new Point(100,100));
}

{% endhighlight %}
{% endtabs %}