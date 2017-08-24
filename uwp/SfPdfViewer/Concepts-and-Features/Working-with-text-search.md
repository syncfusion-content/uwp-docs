---
layout: post
title: Working with text search in Syncfusion Essential UWP PDF viewer.
description: Working with text search in Syncfusion Essential UWP PDF viewer.
platform: uwp
control: PDF viewer
documentation: ug
---

## Working with text search

Text search can be done in two ways, by using the SearchText method or by using the commands.

**Using search methods**

The following code shows how to initiate the text search using the method.
{% tabs %}
{% highlight c# %}
private void Page_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument loadedDocument = new PdfLoadedDocument(buffer);
    pdfViewer.LoadDocument(loadedDocument);
}

private void Button_Click(object sender, RoutedEventArgs e)
{
    //Searches for the text in the PDF Document.
    pdfViewer.SearchText("the");
}
{% endhighlight %}
{% highlight vbnet %}
Private Sub Page_Loaded(sender As Object, e As RoutedEventArgs)
    Dim loadedDocument As New PdfLoadedDocument(buffer)
    pdfViewer.LoadDocument(loadedDocument)
End Sub

Private Sub Button_Click(sender As Object, e As RoutedEventArgs)
    'Searches for the text in the PDF Document.
    pdfViewer.SearchText("the")
End Sub
{% endhighlight %}
{% endtabs %}
The following code shows how to search for the next instance.
{% tabs %}
{% highlight c# %}
private void Page_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument loadedDocument = new PdfLoadedDocument(buffer);
    pdfViewer.LoadDocument(loadedDocument);
}

private void Button_Click(object sender, RoutedEventArgs e)
{
    //Searches for the text in the PDF Document.
    pdfViewer.SearchNextText("the");
}
{% endhighlight %}
{% highlight vbnet %}
Private Sub Page_Loaded(sender As Object, e As RoutedEventArgs)
    Dim loadedDocument As New PdfLoadedDocument(buffer)
    pdfViewer.LoadDocument(loadedDocument)
End Sub

Private Sub Button_Click(sender As Object, e As RoutedEventArgs)
    'Searches for the text in the PDF Document.
    pdfViewer.SearchNextText("the")
End Sub
{% endhighlight %}
{% endtabs %}
The following code shows how to search for the previous instance.
{% tabs %}
{% highlight c# %}
private void Page_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument loadedDocument = new PdfLoadedDocument(buffer);
    pdfViewer.LoadDocument(loadedDocument);
}

private void Button_Click(object sender, RoutedEventArgs e)
{
    //Searches for the text in the PDF Document.
    pdfViewer.SearchPrevText("the");
}
{% endhighlight %}
{% highlight vbnet %}
Private Sub Page_Loaded(sender As Object, e As RoutedEventArgs)
    Dim loadedDocument As New PdfLoadedDocument(buffer)
    pdfViewer.LoadDocument(loadedDocument)
End Sub

Private Sub Button_Click(sender As Object, e As RoutedEventArgs)
    'Searches for the text in the PDF Document.
    pdfViewer.SearchPrevText("the")
End Sub
{% endhighlight %}
{% endtabs %}

**Using search commands**

The following code shows how to search for the next instance using SearchNextCommand.

{% tabs %}
{% highlight xaml %}
<Grid>
        <syncfusion:SfPdfViewerControl Name="pdfViewer"></syncfusion:SfPdfViewerControl>
        <Button Content="Search Next" Command="{Binding ElementName=pdfViewer, Path=SearchNextCommand}" CommandParameter="{Binding Text, ElementName=PageSearchTxtBox}"></Button>
</Grid>
{% endhighlight %}
{% endtabs %}
The following code shows how to search for the previous instance using SearchPreviousCommand.
{% tabs %}
{% highlight xaml %}
<Grid>
        <syncfusion:SfPdfViewerControl Name="pdfViewer"></syncfusion:SfPdfViewerControl>
        <Button Content="Search Next" Command="{Binding ElementName=pdfViewer, Path=SearchPreviousCommand}" CommandParameter="{Binding Text, ElementName=PageSearchTxtBox}"></Button>
</Grid>
{% endhighlight %}
{% endtabs %}

N> The text search operations can only be performed after the display of the PDF document in the viewer control and this cannot be initiated immediately after loading the PDF document.
