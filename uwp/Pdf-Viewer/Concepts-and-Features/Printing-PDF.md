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

The following code shows how to perform the print operation using Print method. Here 'buffer' is the byte array read from the PDF file either using FileOpenPicker or from Assets folder, as illustrated in the [Viewing PDF](https://help.syncfusion.com/uwp/sfpdfviewer/concepts-and-features/viewing-pdf) section. 

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


## Printing Events

PDF viewer provides the following print events.

1.	PrintStarted
2.	PrintProgress
3.	PrintCompleted

You can use the `SfPdfViewerControl.PrintStarted` event to detect the printing process has been initialized and started to print the PDF document using SfPdfViewer. Please refer to the following code sample,

{% tabs %}
{% highlight c# %}

SfPdfViewerControl pdfViewer = new SfPdfViewerControl();
pdfViewer.PrintStarted += PdfViewer_PrintStarted;

private void PdfViewer_PrintStarted(object sender, Syncfusion.Windows.PdfViewer.PrintStartedEventArgs e)
{
    //Event will be raised when SfPdfViewerControl started to print the PDF document 
}

{% endhighlight %}
{% highlight vbnet %}

Dim pdfViewer As SfPdfViewerControl = New SfPdfViewerControl()
pdfViewer.PrintStarted += PdfViewer_PrintStarted
Private Sub PdfViewer_PrintStarted(ByVal sender As Object, ByVal e As Syncfusion.Windows.PdfViewer.PrintStartedEventArgs)
 'Event will be raised when SfPdfViewerControl started to print the PDF document 
End Sub

{% endhighlight %}
{% endtabs %}

You can use the `SfPdfViewerControl.PrintProgress` event to detect the printing progress of PDF document using the SfPdfViewer. The properties that gives the current page index of the PDF page being printed and total page count, can be obtained using the `PrintProgressEventArgs` parameter of the event’s handler. Please refer to the following code sample,

{% tabs %}
{% highlight c# %}

SfPdfViewerControl pdfViewer = new SfPdfViewerControl();
pdfViewer.PrintProgress += PdfViewer_PrintProgress;

private void PdfViewer_PrintProgress(object sender, PrintProgressEventArgs e)
    {
        //Get the page index currently being printed
         int printPageIndex = e.PageIndex;

        //Get the total page count of PDF document is being printed
         int totalPageCount = e.PageCount;
    }


{% endhighlight %}
{% highlight vbnet %}

Dim pdfViewer As SfPdfViewerControl = New SfPdfViewerControl()
pdfViewer.PrintProgress += PdfViewer_PrintProgress

Private Sub PdfViewer_PrintProgress(ByVal sender As Object, ByVal e As PrintProgressEventArgs)
    'Get the page index currently being printed
    Dim printPageIndex As Integer = e.PageIndex
	'Get the total page count of PDF document is being printed
    Dim totalPageCount As Integer = e.PageCount
End Sub

{% endhighlight %}
{% endtabs %}

You can use the `SfPdfViewerControl.PrintCompleted` event to detect the completion status of the printing process of PDF document using the SfPdfViewer. The properties that provide the print completion status of the PDF page can be obtained using the `PrintCompletedEventArgs` parameter of the event’s handler. Please refer to the following code sample,

{% tabs %}
{% highlight c# %}

SfPdfViewerControl pdfViewer = new SfPdfViewerControl();
pdfViewer.PrintCompleted += PdfViewer_PrintCompleted

private void PdfViewer_PrintCompleted(object sender, PrintCompletedEventArgs e)
        {
            //Specifies the completion status of a print task.
            PrintTaskCompletion completion = e.PrintTaskCompletion;

            
            if (completion == PrintTaskCompletion.Abandoned)
            {
                    //Indicates the printing process has been abandoned
            }
            
            else if (completion == PrintTaskCompletion.Canceled)
            {
                   //Indicates the printing process has been cancelled by the user
            }
            
            else if (completion == PrintTaskCompletion.Failed)
            {
                   //Indicates the printing process has been failed automatically
            }
            
            else if (completion == PrintTaskCompletion.Submitted)
            {
                  //Indicates the succesfull completion of printing process
            }
        }

{% endhighlight %}
{% highlight vbnet %}

Dim pdfViewer As SfPdfViewerControl = New SfPdfViewerControl()
pdfViewer.PrintProgress += PdfViewer_PrintProgress

Private Sub PdfViewer_PrintCompleted(ByVal sender As Object, ByVal e As PrintCompletedEventArgs)
    'Specifies the completion status of a print task.
    Dim completion As PrintTaskCompletion = e.PrintTaskCompletion

    If completion = PrintTaskCompletion.Abandoned Then 
	'Indicates the printing process has been abandoned
    ElseIf completion = PrintTaskCompletion.Canceled Then 
	'Indicates the printing process has been cancelled by the user
    ElseIf completion = PrintTaskCompletion.Failed Then 
	'Indicates the printing process has been failed automatically
    ElseIf completion = PrintTaskCompletion.Submitted Then 
	'Indicates the succesfull completion of printing process
    End If
End Sub

{% endhighlight %}
{% endtabs %}

N> The SfPdfViewer control for UWP does not support silent printing and so this method can be used only when the PDF document is displayed in the PDF viewer.
