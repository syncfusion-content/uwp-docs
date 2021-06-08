---
layout: post
title: Get page offset collection in Syncfusion Essential UWP PDF viewer.
description: Learn here about Get page offset collection support in UWP PDF viewer control with page numbers as keys and the corresponding vertical location, and more.
platform: uwp
control: PDF viewer
documentation: ug
---

# Get page offset collection in UWP PDF Viewer
Page offset collection is a dictionary with page numbers as keys and the corresponding vertical location where the page ends as values. The following code example illustrates accessing the same. Here 'buffer' is the byte array read from the PDF file either using FileOpenPicker or from Assets folder, as illustrated in the [Viewing PDF](https://help.syncfusion.com/uwp/sfpdfviewer/concepts-and-features/viewing-pdf) section.
{% tabs %}
{% highlight c# %}
private void Page_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument loadedDocument = new PdfLoadedDocument(buffer);
    pdfViewer.LoadDocument(loadedDocument);
}

private void Button_Click(object sender, RoutedEventArgs e)
{
    //Gets the page offset collection.
    Dictionary<int, double> offsetCollection = pdfViewer.PageOffsetCollection;
}
{% endhighlight %}
{% highlight vbnet %}
Private Sub Page_Loaded(sender As Object, e As RoutedEventArgs)
    Dim loadedDocument As New PdfLoadedDocument(buffer)
    pdfViewer.LoadDocument(loadedDocument)
End Sub

Private Sub Button_Click(sender As Object, e As RoutedEventArgs)
    'Gets the page offset collection.
    Dim offsetCollection As Dictionary(Of Integer, Double) = pdfViewer.PageOffsetCollection
End Sub
{% endhighlight %}
{% endtabs %}

N> The page offset collection will be generated only at the time of display of the PDF document in the viewer, when tried before the display of the document this would return a dictionary of count 0.
