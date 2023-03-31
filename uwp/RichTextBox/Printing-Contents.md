---
title: Printing Contents in UWP RichTextBox control | Syncfusion
description: Learn here all about Printing Contents support in Syncfusion UWP RichTextBox (SfRichTextBoxAdv) control and more.
platform: uwp
control: SfRichTextBoxAdv
documentation: ug
keywords: printing
---
# Printing Contents in UWP RichTextBox (SfRichTextBoxAdv)

The SfRichTextBoxAdv supports API to retrieve each page as a bitmap image by specifying the page number. Using this API and Print manager support, you can easily achieve printing contents of SfRichTextBoxAdv page by page in Universal Windows Platform applications.
The following sample code demonstrates how to register for printing and how to implement print document event handlers.
{% tabs %}
{% highlight c# %}
// Initializes a list of BitmapImage to store images of pages.
List<BitmapImage> pageImages = new List<BitmapImage>();

// Initializes PrintDocument instance.
PrintDocument printDocument = new PrintDocument();
IPrintDocumentSource printDocumentSource;

// Registers for Printing
void RegisterForPrinting()
{
    // Hooks print task requested event handler.
    PrintManager printManager = PrintManager.GetForCurrentView();
    printManager.PrintTaskRequested += PrintManager_PrintTaskRequested;

    // Initializes the print document source.
    printDocumentSource = printDocument.DocumentSource;

    // Hooks print document event handlers.
    printDocument.Paginate += PrintDocument_Paginate;
    printDocument.GetPreviewPage += PrintDocument_GetPreviewPage;
    printDocument.AddPages += PrintDocument_AddPages;
}

// Print Task Requested event handler
private void PrintManager_PrintTaskRequested(PrintManager sender, PrintTaskRequestedEventArgs args)
{
    PrintTask printTask = null;
    printTask = args.Request.CreatePrintTask("Document", sourceRequested =>
    {
        // Prints Task event handler invoked when the print job is completed.
        printTask.Completed += PrintTask_Completed;
        sourceRequested.SetSource(printDocumentSource);
    });
}

// Print Task Completed Event Handler
private void PrintTask_Completed(PrintTask sender, PrintTaskCompletedEventArgs args)
{
    pageImages.Clear();
}

// Print Document Paginate event handler.
private void PrintDocument_Paginate(object sender, PaginateEventArgs e)
{
    int pageCount = richTextBoxAdv.PageCount;
    PrintDocument printDocument = sender as PrintDocument;
    // Report the number of preview pages created.
    printDocument.SetPreviewPageCount(pageCount, PreviewPageCountType.Intermediate);
}

// Print Document Get Preview Page event handler.
private void PrintDocument_GetPreviewPage(object sender, GetPreviewPageEventArgs e)
{
    PrintDocument printDocument = sender as PrintDocument;
    int currentPreviewPage = 0;
    Interlocked.Exchange(ref currentPreviewPage, e.PageNumber - 1);
    if (pageImages.Count >= e.PageNumber)
    {
        BitmapImage bitmap = pageImages[e.PageNumber - 1];
        Image image = new Image();
        image.Source = bitmap;
        printDocument.SetPreviewPage(e.PageNumber, image);
    }
}

// Print Document Add Pages event handler.
private void PrintDocument_AddPages(object sender, AddPagesEventArgs e)
{
    int pageCount = richTextBoxAdv.PageCount;
    for (int i = 0; i < pageImages.Count; i++)
    {
        Image image = new Image();
        image.Source = pageImages[i];
        printDocument.AddPage(image);
    }
    printDocument.AddPagesComplete();
}



{% endhighlight %}

{% endtabs %}

The following code example demonstrates how to retrieve each page in SfRichTextBoxAdv as bitmap image and how to invoke printing.
{% tabs %}
{% highlight c# %}
// Gets the page images asynchronously.
async Task<bool> GetPageImagesAsync()
{
    TaskCompletionSource<bool> taskCompletionSource = new TaskCompletionSource<bool>();
    // Clears the page images.
    pageImages.Clear();
    int pageCount = richTextBoxAdv.PageCount;
    for (int i = 0; i < pageCount; i++)
    {
        // Retrieve page in RichTextBoxAdv as BitmapImage by specifying page number.
        BitmapImage bitmapImage = await richTextBoxAdv.GetPageAsImageAsync(i);
        pageImages.Add(bitmapImage);
    }
    taskCompletionSource.SetResult(true);
    return await taskCompletionSource.Task;
}

// Invokes printing asynchronously.
async void InvokePrintAsync()
{
    bool pagesRetrieved = await GetPageImagesAsync();
    if (pagesRetrieved)
        await PrintManager.ShowPrintUIAsync();
}



{% endhighlight %}

{% endtabs %}

The following code example demonstrates how to unregister printing and print document event handlers.
{% tabs %}
{% highlight c# %}
// Unregisters printing.
void UnRegisterPrinting()
{
    // Unhooks the print document event handlers.
    if (printDocument != null)
    {
        printDocument.Paginate -= PrintDocument_Paginate;
        printDocument.GetPreviewPage -= PrintDocument_GetPreviewPage;
        printDocument.AddPages -= PrintDocument_AddPages;
        printDocumentSource = null;
        printDocument = null;
    }
    // Unhooks the print task requested event handler.
    PrintManager printManager = PrintManager.GetForCurrentView();
    printManager.PrintTaskRequested -= PrintManager_PrintTaskRequested;
}



{% endhighlight %}

{% endtabs %}

In the SfRichTextBoxAdv control, comments will be shown by default on printing the document. You can hide the comments while printing by using the [PrintComments](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.RichTextBoxAdv.EditorSettings.html#Syncfusion_UI_Xaml_RichTextBoxAdv_EditorSettings_PrintComments) property of [EditorSettings](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.RichTextBoxAdv.EditorSettings.html) class.

The following code example illustrates how to hide the comments on printing the document.

{% tabs %}
{% highlight xaml %}
<RichTextBoxAdv:SfRichTextBoxAdv x:Name="richTextBoxAdv">
    <RichTextBoxAdv:SfRichTextBoxAdv.EditorSettings>
        <RichTextBoxAdv:EditorSettings PrintComments="False" />
    </RichTextBoxAdv:SfRichTextBoxAdv.EditorSettings>
</RichTextBoxAdv:SfRichTextBoxAdv>

{% endhighlight %}
{% highlight c# %}
SfRichTextBoxAdv richTextBoxAdv = new SfRichTextBoxAdv();
richTextBoxAdv.EditorSettings.PrintComments = false;

{% endhighlight %}
{% highlight VB %}
Dim richTextBoxAdv As New SfRichTextBoxAdv()
richTextBoxAdv.EditorSettings.PrintComments = False

{% endhighlight %}
{% endtabs %}
