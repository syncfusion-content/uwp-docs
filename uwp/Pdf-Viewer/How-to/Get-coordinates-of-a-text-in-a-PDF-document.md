---
layout: post
title: Get coordinates of a text in a PDF document in Syncfusion Essential UWP PDF viewer.
description: Get coordinates of a text in a PDF document in Syncfusion Essential UWP PDF viewer.
platform: uwp
control: PDF viewer
documentation: ug
---

# Get coordinates of a text in a PDF document in UWP PDF Viewer
The SfPdfViewer control allows you to acquire the coordinates of multiple instances of a particular text in a page of the PDF document. The following code illustrates the same. Here 'buffer' is the byte array read from the PDF file either using FileOpenPicker or from Assets folder, as illustrated in the [Viewing PDF](https://help.syncfusion.com/uwp/sfpdfviewer/concepts-and-features/viewing-pdf) section. 
{% tabs %}
{% highlight c# %}
private void Page_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument loadedDocument = new PdfLoadedDocument(buffer);
    pdfViewer.LoadDocument(loadedDocument);
}

private void Button_Click(object sender, RoutedEventArgs e)
{
    //Creates an instance to get the list of PdfTextCoordinates.
    List<PdfTextCoordinates> coordinates = new List<PdfTextCoordinates>();
    //Searches for the existence of a text and gets the text positions in a PDF page.
    pdfViewer.GetTextCoordinates("example", 4, out coordinates);
}
{% endhighlight %}
{% highlight vbnet %}
Private Sub Page_Loaded(sender As Object, e As RoutedEventArgs)
    Dim loadedDocument As New PdfLoadedDocument(buffer)
    pdfViewer.LoadDocument(loadedDocument)
End Sub

Private Sub Button_Click(sender As Object, e As RoutedEventArgs)
    'Creates an instance to get the list of PdfTextCoordinates. 
    Dim coordinates As New List(Of PdfTextCoordinates)()
    'Searches for the existence of a text and gets the text positions in a PDF page.
    pdfViewer.GetTextCoordinates("example", 4, coordinates)
End Sub
{% endhighlight %}
{% endtabs %}

N> Getting coordinates of a text will work only after the display of the PDF document in the viewer, when tried before the display of the PDF document the out value will be a list of count 0.
