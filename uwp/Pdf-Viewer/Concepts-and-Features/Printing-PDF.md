---
layout: post
title: Printing PDF in UWP PDF Viewer control | Syncfusion
description: Learn here all about Printing PDF support in Syncfusion UWP PDF Viewer (SfPdfViewer) control and more.
platform: uwp
control: PDF viewer
documentation: ug
---

# Printing PDF in UWP PDF Viewer (SfPdfViewer)

Printing can be done using the Print method or by using the Print command.

The following code shows how to perform the print operation using Print method. Here 'buffer' is the byte array read from the PDF file either using FileOpenPicker or from Assets folder, as illustrated in the [Viewing PDF](https://help.syncfusion.com/uwp/pdf-viewer/concepts-and-features/viewing-pdf) section. 

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

## Printing PDF Asynchronously

The PDF Viewer allows you to print the PDF document asynchronously using the `PrintAsync` method. You can also cancel the asynchronous printing when it is in progress.

{% tabs %}
{% highlight c# %}

//Asynchronously  prints the document loaded in the PDF viewer 
pdfViewer.PrintAsync(cancellationTokenSource);

{% endhighlight %}
{% endtabs %}

In the above code sample, the `cancellationTokenSource` enables you to cancel the asynchronous printing when it is in progress

### Cancel the asynchronous PDF printing

You can raise the cancel request when printing is in progress

{% tabs %}
{% highlight c# %}

private void cancelButton_Clicked(object sender, EventArgs e)
 { 
   cancellationTokenSource.Cancel();
 }
 
{% endhighlight %}
{% endtabs %}

 In the above code sample, the cancellationTokenSource instance is the same as the one given as the argument when printing the PDF document asynchronously.
 
 N> Calling the above method will not have any effect once the printing is complete. It will stop the printing process only when it is in progress.
 
### Handling exceptions while performing the asynchronous print

When the `PrintAsync` is called, the PDF Viewer will show the print previewer. Exceptions will be thrown if the print cannot be performed. The exceptions will be propagated back to the caller of this method. We recommend catching these exceptions as follows.

{% tabs %}
{% highlight c# %}

  private void printButton_Clicked(object sender, EventArgs e)
        {
            try
            {
                
                //Sets the name of the printed document.
                pdfViewer.PrinterSettings.DocumentName = “PdfFileName.pdf”;

                //Asynchronously  prints the document loaded in the PDF viewer 
                await pdfViewerControl.PrintAsync(cancellationToken);
            }
            catch (Exception e)
            {
                ContentDialog printErrorDialog = new ContentDialog()
                {
                    Title = "Printing error",
                    Content = "Printing cannot proceed at this time.",
                    PrimaryButtonText = "OK"
                };
                await printErrorDialog.ShowAsync();
            }
        } 
{% endhighlight %}
{% endtabs %}


N> The [`SfPdfViewer`](https://help.syncfusion.com/cr/uwp/Syncfusion.Windows.PdfViewer.SfPdfViewerControl.html) control for UWP does not support silent printing and so this method can be used only when the PDF document is displayed in the PDF viewer.


## Quality factor for print

The PDF Viewer allows the user to set and retrieve the quality factor for print by using the [`QualityFactor`](https://help.syncfusion.com/cr/uwp/Syncfusion.Windows.PdfViewer.PrinterSettings.html#Syncfusion_Windows_PdfViewer_PrinterSettings_QualityFactor) property. The default value of this API is set to 1, and the values are restricted between 1 and 5. The values falling below the range are taken as 1, which represents the lowest page quality, and those above the range are taken as 5, which represents the highest page quality.
Refer to the following code sample to set the quality factor for the print.

{% highlight c# %}

//Sets the quality factor for the print.
pdfViewer.PrinterSettings.QualityFactor = 2;

{% endhighlight %}

N> Printing with quality factors higher than 2 will work as expected in the x64 configuration but may cause System.OutOfMemoryException in the x86 configuration due to the limited memory capacity of this architecture.

## Customizing the print previewer

You can customize the print options displayed in the print previewer while performing a print operation in the PDF Viewer control. The event `PrintTaskRequested` will be raised when you call the Print method to print a PDF document.

{% tabs %}
{% highlight c# %}

//Wire up the PrintTaskRequested event with the PdfViewer_PrintTaskRequested
pdfViewer.PrintTaskRequested += PdfViewer_PrintTaskRequested;

{% endhighlight %}
{% endtabs %}

In the `PrintTaskRequested` event handler, you can include the required print options such as the number of copies, collation, duplex, and more by creating a `PrintTask` using the properties `Request` and `PrintDocumentSource`. Refer to the following code example.

{% tabs %}
{% highlight c# %}

private void PdfViewer_PrintTaskRequested(object sender, SfPdfViewerPrintTaskRequestedEventArgs e)
        {
            PrintTask printTask = null;
            
           //Create a print task to customize the print options
            printTask = e.Request.CreatePrintTask("Printing", sourceRequested =>
            {

                PrintTaskOptionDetails printDetailedOptions = PrintTaskOptionDetails.GetFromPrintTaskOptions(printTask.Options);
                IList<string> displayedOptions = printDetailedOptions.DisplayedOptions;

                //Allows to add the required print options
                displayedOptions.Add(Windows.Graphics.Printing.StandardPrintTaskOptions.CustomPageRanges);
                printTask.Options.PageRangeOptions.AllowCurrentPage = true;
                printTask.Options.PageRangeOptions.AllowAllPages = true;
                printTask.Options.PageRangeOptions.AllowCustomSetOfPages = true;

                // Set the pdfViewerControl�s print document source
                sourceRequested.SetSource(e.PrintDocumentSource);
                e.PrintTask = printTask;

            });

        }

{% endhighlight %}
{% endtabs %}

Refer to the following code example to disable the print preview,

{% tabs %}
{% highlight c# %}

pdfViewerControl.PrintTaskRequested+= PrintTaskRequested;
        private void PrintTaskRequested(object sender, SfPdfViewerPrintTaskRequestedEventArgs e)
        {
            PrintTask printTask = null;
            printTask = e.Request.CreatePrintTask("Printing", sourceRequested =>
            {

                // Set the SfPdfViewerControl�s print document source
                sourceRequestedArgs.SetSource(e.PrintDocumentSource);

            });
            printTask.IsPreviewEnabled = false;
            e.PrintTask = printTask;
        }

{% endhighlight %}
{% endtabs %}

N>Though if you specify any print options to be displayed, only those that are supported by the selected printer are shown in the print preview UI. The print UI won't show options that the selected printer doesn't support. The print options will appear in the order in which they are added.
