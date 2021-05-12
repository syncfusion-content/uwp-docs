---
title: Import and Export in UWP RichTextBox control | Syncfusion
description: Learn here all about Import and Export support in Syncfusion UWP RichTextBox (SfRichTextBoxAdv) control and more.
platform: uwp
control: SfRichTextBoxAdv
documentation: ug
keywords: import, export, load, save
---
# Import and Export in UWP RichTextBox (SfRichTextBoxAdv)

The SfRichTextBoxAdv allows you to import/export word documents (.docx, .doc), rich text format documents (.rtf), HTML documents (.htm, .html) and text documents (.txt).
The following sample code demonstrates how to import contents from storage file into SfRichTextBoxAdv.
{% tabs %}
{% highlight c# %}
// Imports the document asynchronously.
async void ImportDocumentAsync()
{
    // Initializes the file open picker.
    FileOpenPicker fileOpenPicker = new FileOpenPicker();
    fileOpenPicker.FileTypeFilter.Add(".docx");
    fileOpenPicker.FileTypeFilter.Add(".doc");
    fileOpenPicker.FileTypeFilter.Add(".rtf");
    fileOpenPicker.FileTypeFilter.Add(".htm");
    fileOpenPicker.FileTypeFilter.Add(".html");
    fileOpenPicker.FileTypeFilter.Add(".txt");

    // Picks single storage file using file open picker.
    StorageFile storageFile = await fileOpenPicker.PickSingleFileAsync();

    if (storageFile != null)
        // Loads the storage file into RichTextBoxAdv asynchronously.
        await richTextBoxAdv.LoadAsync(storageFile);
}


{% endhighlight %}

{% endtabs %}

The following code example demonstrates how to export SfRichTextBoxAdv contents as storage file.
{% tabs %}
{% highlight c# %}
// Exports the document asynchronously.
async void ExportDocumentAsync()
{
    // Initializes the file save picker.
    FileSavePicker fileSavePicker = new FileSavePicker();
    fileSavePicker.FileTypeChoices.Add("Word Document", new List<string>() { ".docx" });
    fileSavePicker.FileTypeChoices.Add("Word 97-2003 Document", new List<string>() { ".doc" });
    fileSavePicker.FileTypeChoices.Add("Rich Text Format", new List<string>() { ".rtf" });
    fileSavePicker.FileTypeChoices.Add("HTML Document", new List<string>() { ".html" });
    fileSavePicker.FileTypeChoices.Add("Text Document", new List<string>() { ".txt" });

    // Picks the storage file to save.
    StorageFile storageFile = await fileSavePicker.PickSaveFileAsync();

    if (storageFile != null)
        // Saves RichTextBoxAdv content into the storage file asynchronously.
        await richTextBoxAdv.SaveAsync(storageFile);
}


{% endhighlight %}

{% endtabs %}

N> When the SfRichTextBoxAdv control encounters an unsupported element, it does not render the element, instead, it continues to the next supported element and render it. Examples of unsupported elements are AutoShapes, watermarks, charts, SmartArt, WordArt, equations, document structure tags, styles, wrapping styles, fields other than hyperlinks, absolutely positioned tables, and absolutely positioned images.

## Asynchronous import settings

### Show or hide the loading page number

The SfRichTextBoxAdv control shows the current loading page number by default at the bottom right corner of the control while loading the document asynchronously. You can hide this loading page number by using the ShowPageNumber property of LoadAsyncSettings class.

The following code example demonstrates how to hide the loading page number in SfRichTextBoxAdv control.

{% tabs %}
{% highlight xaml %}
<RichTextBoxAdv:SfRichTextBoxAdv x:Name="richTextBoxAdv">
       <RichTextBoxAdv:SfRichTextBoxAdv.LoadAsyncSettings>
           <RichTextBoxAdv:LoadAsyncSettings ShowPageNumber="False"/>
       </RichTextBoxAdv:SfRichTextBoxAdv.LoadAsyncSettings>
</RichTextBoxAdv:SfRichTextBoxAdv>


{% endhighlight %}
{% highlight c# %}
// Initializes a new instance of RichTextBoxAdv.
SfRichTextBoxAdv richTextBoxAdv = new SfRichTextBoxAdv();
////Hides the loading page number.
richTextBoxAdv.LoadAsyncSettings.ShowPageNumber = false;


{% endhighlight %}
{% highlight VB %}
' Initializes a new instance of RichTextBoxAdv.
Dim richTextBoxAdv As New SfRichTextBoxAdv()
' Hides the loading page number.
richTextBoxAdv.LoadAsyncSettings.ShowPageNumber = false


{% endhighlight %}

{% endtabs %}

N> This API is supported starting from release version v17.4.0.X.


## Events to notify document starts and completes loading and saving

SfRichTextBoxAdv control also provides below events to notify document starts and completes loading and saving.


### Events Table

<table>
<tr>
<th>
Event </th><th>
Description </th></tr>
<tr>
<td>
DocumentChanging</td><td>
This event is triggered when the document starts loading.</td></tr>
<tr>
<td>
DocumentChanged</td><td>
This event is triggered after the document is successfully loaded.</td></tr>
<tr>
<td>
DocumentSaving</td><td>
This event is triggered when the document starts saving.</td></tr>
<tr>
<td>
DocumentSaved</td><td>
This event is triggered after the document is successfully saved.</td></tr>
</table>

N> This API is supported starting from release version v18.2.0.X.
