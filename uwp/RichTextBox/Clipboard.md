---
title: Clipboard in UWP RichTextBox control | Syncfusion
description: Learn here all about Clipboard support in Syncfusion UWP RichTextBox (SfRichTextBoxAdv) control and more.
platform: uwp
control: SfRichTextBoxAdv
documentation: ug
keywords: clipboard
---
# Clipboard in UWP RichTextBox (SfRichTextBoxAdv)

The SfRichTextBoxAdv takes advantage of the clipboard support and allows you to copy or paste contents to and from the clipboard in the following formats.

* Rich text format.

* Text.

* Image.

## UI Command to access clipboard operations


The following code example demonstrates how to bind commands for accessing clipboard operations.
{% tabs %}
{% highlight xaml %}
<!-- Binds button to the CutCommand -->
<Button Content="Cut" Command="{Binding ElementName=richTextBoxAdv, Path=CutCommand, Mode=TwoWay}" />
<!-- Binds button to the CopyCommand -->
<Button Content="Copy" Command="{Binding ElementName=richTextBoxAdv, Path=CopyCommand, Mode=TwoWay}" />
<!-- Binds button to the PasteCommand -->
<Button Content="Paste" Command="{Binding ElementName=richTextBoxAdv, Path=PasteCommand, Mode=TwoWay}" />


{% endhighlight %}
{% highlight c# %}
/// <summary>
/// Cut the selected contents of SfRichTextBoxAdv.
/// </summary>
public void Cut()
{
    // Executes cut command.
    if (richTextBoxAdv.CutCommand.CanExecute(null))
        richTextBoxAdv.CutCommand.Execute(null);
}
/// <summary>
/// Copy the selected contents of SfRichTextBoxAdv.
/// </summary>
public void Copy()
{
    // Executes copy command.
    if (richTextBoxAdv.CopyCommand.CanExecute(null))
        richTextBoxAdv.CopyCommand.Execute(null);
}
/// <summary>
/// Paste the clipboard contents to SfRichTextBoxAdv in current selection.
/// </summary>
public void Paste()
{
    // Executes paste command.
    if (richTextBoxAdv.PasteCommand.CanExecute(null))
        richTextBoxAdv.PasteCommand.Execute(null);
}
{% endhighlight %}
{% endtabs %}

N> In order to cut, copy or paste, the standard keyboard shortcuts such as CTRL + X, CTRL + C, CTRL + V can also be used.
