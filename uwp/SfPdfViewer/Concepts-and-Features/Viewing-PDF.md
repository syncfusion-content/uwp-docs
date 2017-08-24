---
layout: post
title: Viewing PDF in Syncfusion Essential UWP PDF viewer.
description: Viewing PDF in Syncfusion Essential UWP PDF viewer.
platform: uwp
control: PDF viewer
documentation: ug
---

## Viewing PDF
The SfPdfViewer has the ability to load PDF documents from stream and PdfLoadedDocument object.
The below code explains how to load the document using a PdfLoadedDocument object.
{% tabs %}
{% highlight c# %}
PdfLoadedDocument loadedDocument = new PdfLoadedDocument(buffer);
pdfViewer.LoadDocument(loadedDocument);
{% endhighlight %}
{% highlight vbnet %}
Dim loadedDocument As New PdfLoadedDocument(Buffer)
pdfViewer.LoadDocument(loadedDocument)
{% endhighlight %}
{% endtabs %}
The below code explains how to load the document from stream.
{% tabs %}
{% highlight c# %}
var picker = new FileOpenPicker();
picker.SuggestedStartLocation = PickerLocationId.DocumentsLibrary;
picker.ViewMode = PickerViewMode.List;
picker.FileTypeFilter.Add(".pdf");
var file = await picker.PickSingleFileAsync();
if (file == null) 
    return;
var stream = await file.OpenAsync(Windows.Storage.FileAccessMode.Read);
Stream fileStream = stream.AsStreamForRead();
pdfViewer.LoadDocument(fileStream);
{% endhighlight %}
{% highlight vbnet %}
Dim picker = New FileOpenPicker()
picker.SuggestedStartLocation = PickerLocationId.DocumentsLibrary
picker.ViewMode = PickerViewMode.List
picker.FileTypeFilter.Add(".pdf")
Dim file = Await picker.PickSingleFileAsync()
If file Is Nothing Then
    Return
End If
Dim stream = Await file.OpenAsync(Windows.Storage.FileAccessMode.Read)
Dim fileStream As Stream = stream.AsStreamForRead()
pdfViewer.LoadDocument(fileStream)
{% endhighlight %}
{% endtabs %}
