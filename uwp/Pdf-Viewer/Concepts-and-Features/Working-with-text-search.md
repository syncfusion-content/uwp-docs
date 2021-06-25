---
layout: post
title: Working with text search in UWP PDF Viewer control | Syncfusion
description: Learn here all about Working with text search support in Syncfusion UWP PDF Viewer (SfPdfViewer) control and more.
platform: uwp
control: PDF viewer
documentation: ug
---

# Working with text search in UWP PDF Viewer (SfPdfViewer)

Text search can be done in two ways, by using the SearchText method or by using the commands.

In all code snippets found below, 'buffer' is the byte array read from the PDF file either using FileOpenPicker or from Assets folder, as illustrated in the [Viewing PDF](https://help.syncfusion.com/uwp/sfpdfviewer/concepts-and-features/viewing-pdf) section. 

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

**Using asynchronous search methods**

The PDF viewer allows the users to perform text search asynchronously using the [SearchTextAsync](https://help.syncfusion.com/cr/uwp/Syncfusion.Windows.PdfViewer.SfPdfViewerControl.html#Syncfusion_Windows_PdfViewer_SfPdfViewerControl_SearchTextAsync_System_String_System_Threading_CancellationToken_) method. The user can also cancel the asynchronous text search when it is in progress.

{% tabs %}
{% highlight c# %}
CancellationTokenSource cts = new CancellationTokenSource();

private void Page_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument loadedDocument = new PdfLoadedDocument(buffer);
    pdfViewer.LoadDocument(loadedDocument);
}

private void SearchButton_Click(object sender, RoutedEventArgs e)
{
    //Searches for the text in the PDF Document.
    pdfViewer.SearchTextAsync(targetText, cts.Token);
}

private void CancelButton_Click(object sender, RoutedEventArgs e)
{
   cts.Cancel();
}

{% endhighlight %}
{% endtabs %}

In the above code sample, the `targetText` is the input text to be searched and the `cancellationToken` enables the users to cancel the asynchronous text search.

The following code explains how to search for the next instance of the text asynchronously.

{% tabs %}
{% highlight c# %}

CancellationTokenSource cts = new CancellationTokenSource();

private void SearchNextButton_Click(object sender, RoutedEventArgs e)
{
    //Searches for the next text instance in the PDF Document.
    pdfViewer.SearchNextTextAsync(targetText, cts.Token);
}

private void CancelButton_Click(object sender, RoutedEventArgs e)
{
   cts.Cancel();
}

{% endhighlight %}
{% endtabs %}

The following code explains how to search for the previous instance of the text asynchronously. 

{% tabs %}
{% highlight c# %}

CancellationTokenSource cts = new CancellationTokenSource();

private void SearchPreviousButton_Click(object sender, RoutedEventArgs e)
{
    //Searches for the previous instance of the text in the PDF Document.
    pdfViewer.SearchPreviousTextAsync(targetText, cts.Token);
}

private void CancelButton_Click(object sender, RoutedEventArgs e)
{
   cts.Cancel();
}

{% endhighlight %}
{% endtabs %}

N> The text search operations can only be performed after the display of the PDF document in the viewer control and this cannot be initiated immediately after loading the PDF document.
