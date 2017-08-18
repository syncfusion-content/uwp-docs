---
layout: post
title: Printing PDF in Syncfusion Essential UWP PDF viewer.
description: Printing PDF in Syncfusion Essential UWP PDF viewer.
platform: uwp
control: PDF viewer
documentation: ug
---

## Printing PDF

Printing can be done using the Print method or by using the Print command.

The following code shows how to perform the print operation using Print method

{% tabs %}
{% highlight c# %}
private void Page_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument loadedDocument = new PdfLoadedDocument(buffer);
    pdfViewer.LoadDocument(loadedDocument);
}

private void Button_Click(object sender, RoutedEventArgs e)
{
    //Prints the document loaded in the PDF viewer
    pdfViewer.Print();
}
{% endhighlight %}
{% highlight vbnet %}
Private Sub Page_Loaded(sender As Object, e As RoutedEventArgs)
    Dim loadedDocument As New PdfLoadedDocument(buffer)
    pdfViewer.LoadDocument(loadedDocument)
End Sub

Private Sub Button_Click(sender As Object, e As RoutedEventArgs)
    'Prints the document loaded in the PDF viewer
    pdfViewer.Print()
End Sub
{% endhighlight %}
{% endtabs %}

The following code shows how to bind the PrintCommand to a Button

{% tabs %}
{% highlight xaml %}
<Grid>
        <syncfusion:SfPdfViewerControl Name="pdfViewer"/> 
        <Button Command="{Binding PrintCommand}" />
</Grid>
{% endhighlight %}
{% endtabs %}

N> The SfPdfViewer control for UWP does not support silent printing and so this method can be used only when the PDF document is displayed in the PDF viewer.
