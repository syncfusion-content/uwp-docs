---
layout: post
title: Viewing PDF in UWP PDF Viewer control | Syncfusion
description: Learn here all about Viewing PDF support in Syncfusion UWP PDF Viewer (SfPdfViewer) control and more.
platform: uwp
control: PDF viewer
documentation: ug
---

# Viewing PDF in UWP PDF Viewer (SfPdfViewer)
The [`SfPdfViewer`](https://help.syncfusion.com/cr/uwp/Syncfusion.Windows.PdfViewer.SfPdfViewerControl.html) allows you to load the PDF documents from the [`stream`](https://docs.microsoft.com/en-us/dotnet/api/system.io.stream?view=net-5.0), [`storageFile`](https://docs.microsoft.com/en-us/uwp/api/windows.storage.storagefile?view=winrt-19041), and [`PdfLoadedDocument`](https://help.syncfusion.com/cr/file-formats/Syncfusion.Pdf.Parsing.PdfLoadedDocument.html) object.

## Loading a PDF using PdfLoadedDocument object
The [`SfPdfViewer`](https://help.syncfusion.com/cr/uwp/Syncfusion.Windows.PdfViewer.SfPdfViewerControl.html) allows you to load the PDF document synchronously and asynchronously from the specified pdfLoadedDocument object using the `LoadDocument` and  `LoadDocumentAsync` methods respectively.

The following code explains how to load the document synchronously using a [`PdfLoadedDocument`](https://help.syncfusion.com/cr/file-formats/Syncfusion.Pdf.Parsing.PdfLoadedDocument.html) object that was created from the PDF in the Assets folder of the application.

{% tabs %}
{% highlight c# %}
Assembly assembly = typeof(MainPage).GetTypeInfo().Assembly;
//Loads the stream from the embedded resource.
fileStream = assembly.GetManifestResourceStream("ApplicationNameSpace.Assets.PDFFileName.pdf");
byte[] buffer = new byte[fileStream.Length];
fileStream.Read(buffer, 0, buffer.Length);
//Create a new PDFLoadedDocument object.
PdfLoadedDocument loadedDocument = new PdfLoadedDocument(buffer);
pdfViewer.LoadDocument(loadedDocument);
{% endhighlight %}
{% highlight vbnet %}
'Create a new PDFLoadedDocument object.
Dim loadedDocument As New PdfLoadedDocument(Buffer)
pdfViewer.LoadDocument(loadedDocument)
{% endhighlight %}
{% endtabs %}

The following code explains how to load the document asynchronously using the [`PdfLoadedDocument`](https://help.syncfusion.com/cr/file-formats/Syncfusion.Pdf.Parsing.PdfLoadedDocument.html) object that was created from the PDF in the Assets folder of the application.

{% tabs %}
{% highlight c# %}
//Create a new PDFLoadedDocument object.
PdfLoadedDocument loadedDocument = new PdfLoadedDocument(buffer);
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
await pdfViewer.LoadDocumentAsync(loadedDocument, cancellationTokenSource.Token);
pdfViewer.LoadDocument(loadedDocument);
{% endhighlight %}
{% highlight vbnet %}
'Create a new PDFLoadedDocument object.
Dim loadedDocument As New PdfLoadedDocument(Buffer)
Dim cancellationTokenSource As New CancellationTokenSource()
Await pdfViewer.LoadDocumentAsync(loadedDocument, cancellationTokenSource.Token)
{% endhighlight %}
{% endtabs %}

In the above code sample, the [`CancellationToken`](https://docs.microsoft.com/en-us/dotnet/api/system.threading.cancellationtoken?view=net-5.0) enables you to cancel the asynchronous loading of a PDF document when it is in progress.

## Loading a PDF using Stream object
The [`SfPdfViewer`](https://help.syncfusion.com/cr/uwp/Syncfusion.Windows.PdfViewer.SfPdfViewerControl.html) allows you to load the PDF document synchronously and asynchronously from the specified stream using the `LoadDocument` and `LoadDocumentAsync` methods respectively.

The following code explains how to load the document synchronously using a [`stream`](https://docs.microsoft.com/en-us/dotnet/api/system.io.stream?view=net-5.0) object that was created from the PDF in the Assets folder of the application.

{% tabs %}
{% highlight c# %}
Assembly assembly = typeof(MainPage).GetTypeInfo().Assembly; 
//Loads the stream from the embedded resource.
fileStream = assembly.GetManifestResourceStream("ApplicationNameSpace.Assets.PDFFileName.pdf"); 
pdfViewer.LoadDocument(fileStream);
{% endhighlight %}
{% highlight vbnet %}
'Loads the stream from the embedded resource. 
Dim assembly As Assembly = GetType(MainPage).GetTypeInfo().Assembly 
docStream = assembly.GetManifestResourceStream("ApplicationNameSpace. Assets.PDFFileName.pdf")
pdfViewer.LoadDocument(docStream)
{% endhighlight %}
{% endtabs %}

The following code explains how to load the document asynchronously using a [`stream`](https://docs.microsoft.com/en-us/dotnet/api/system.io.stream?view=net-5.0) object that was created from the PDF in the Assets folder of the application.

{% tabs %}
{% highlight c# %}
Assembly assembly = typeof(MainPage).GetTypeInfo().Assembly; 
//Loads the stream from the embedded resource.
fileStream = assembly.GetManifestResourceStream("ApplicationNameSpace.Assets.PDFFileName.pdf"); 
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
await pdfViewer.LoadDocumentAsync(fileStream, cancellationTokenSource.Token);
{% endhighlight %}
{% highlight vbnet %}
Assembly assembly = typeof(MainPage).GetTypeInfo().Assembly; 
//Loads the stream from the embedded resource.
fileStream = assembly.GetManifestResourceStream("ApplicationNameSpace.Assets.PDFFileName.pdf"); 
Dim cancellationTokenSource As New CancellationTokenSource()
Await pdfViewer.LoadDocumentAsync(fileStream, cancellationTokenSource.Token)
{% endhighlight %}
{% endtabs %}

In the above code sample, the [`CancellationToken`](https://docs.microsoft.com/en-us/dotnet/api/system.threading.cancellationtoken?view=net-5.0) enables you to cancel the asynchronous loading of a PDF document when it is in progress.

## Loading a PDF using the StorageFile object

The [`SfPdfViewer`](https://help.syncfusion.com/cr/uwp/Syncfusion.Windows.PdfViewer.SfPdfViewerControl.html) allows you to load the PDF document synchronously and asynchronously from the specified storage file using the `LoadDocument` and  `LoadDocumentAsync` methods respectively.

The following code explains how to load the document synchronously using a [`StorageFile`](https://docs.microsoft.com/en-us/uwp/api/windows.storage.storagefile?view=winrt-19041) object that was created from the PDF in the Assets folder of the application.

{% tabs %}
{% highlight c# %}
//Opens a file picker.
var picker = new FileOpenPicker();
picker.SuggestedStartLocation = PickerLocationId.DocumentsLibrary;
picker.ViewMode = PickerViewMode.List;
//Filters the PDF files in the documents library.
picker.FileTypeFilter.Add(".pdf");
StorageFile file = await picker.PickSingleFileAsync();
pdfViewer.LoadDocument(file);
{% endhighlight %}
{% highlight vbnet %}
'Opens a file picker. Dim picker = New FileOpenPicker()
picker.SuggestedStartLocation = PickerLocationId.DocumentsLibrary 
picker.ViewMode = PickerViewMode.List 
'Filters the PDF files in the documents library. 
picker.FileTypeFilter.Add(".pdf") 
Dim file = Await picker.PickSingleFileAsync()
pdfViewer.LoadDocument(file)
{% endhighlight %}
{% endtabs %}

The following code explains how to load the document asynchronously using a [`StorageFile`](https://docs.microsoft.com/en-us/uwp/api/windows.storage.storagefile?view=winrt-19041) object that was created from the PDF in the Assets folder of the application.

{% tabs %}
{% highlight c# %}
//Opens a file picker.
var picker = new FileOpenPicker();
picker.SuggestedStartLocation = PickerLocationId.DocumentsLibrary;
picker.ViewMode = PickerViewMode.List;
//Filters the PDF files in the documents library.
picker.FileTypeFilter.Add(".pdf");
StorageFile file = await picker.PickSingleFileAsync();
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
await pdfViewer.LoadDocumentAsync(file, cancellationTokenSource.Token);
{% endhighlight %}
{% highlight vbnet %}
'Opens a file picker. Dim picker = New FileOpenPicker()
picker.SuggestedStartLocation = PickerLocationId.DocumentsLibrary 
picker.ViewMode = PickerViewMode.List 
'Filters the PDF files in the documents library. 
picker.FileTypeFilter.Add(".pdf") 
Dim file = Await picker.PickSingleFileAsync()
Dim cancellationTokenSource As New CancellationTokenSource()
Await pdfViewer.LoadDocument(file, cancellationTokenSource.Token);
{% endhighlight %}
{% endtabs %}

In the above code sample, the [`CancellationToken`](https://docs.microsoft.com/en-us/dotnet/api/system.threading.cancellationtoken?view=net-5.0) enables you to cancel the asynchronous loading of a PDF document when it is in progress.
