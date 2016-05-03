---
title: Import and Export
description: import-and-export
platform: uwp
control: SfRichTextBoxAdv
documentation: ug
keywords: import, export, load, save
---
# Import and Export

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
