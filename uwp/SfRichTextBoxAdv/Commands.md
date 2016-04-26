---
title: Commands
description: commands
platform: uwp
control: SfRichTextBoxAdv
documentation: ug
keywords: commands
---
# Commands

Commands are a way to handle user interface (UI) actions. They are a loosely coupled way to bind the UI to the logic that performs the action. The SfRichTextBoxAdv supports commands for mostly used operations which are classified below.

* Character Formatting – Bold, Italic, Underline, Strikethrough, Baseline Alignment, Font Family, Font Size, Font Color and Highlight Color.

* Paragraph Formatting – Left Indent, Right Indent, First line Indent, Text Alignment, Before Spacing, After Spacing, Line Spacing, Line Spacing Type, Increase Indent, Decrease Indent and Change List Type.

* Clipboard – Cut, Copy and Paste.

* History – Undo and Redo.

* Import and Export – Open Document, Save Document and New Document.

* Comments – New Comment, Delete Comment, Delete All Comments, Previous Comment, Next Comment and Show Comments.

* Table – Insert Table, Insert Row, Insert Column, Delete Table, Delete Row, Delete Column and Merge Selected Cells.

* UI options – Show Hyperlink Dialog and Show Options Pane.

* Other – Insert Picture, Insert Hyperlink and Layout Type.

## UI Command to access character formatting


The following code example demonstrates how to bind commands for applying character format.
{% tabs %}
{% highlight xaml %}
<!-- Binds button to the BoldCommand -->
<Button Content="Bold" Command="{Binding ElementName=richTextBoxAdv, Path=BoldCommand, Mode=TwoWay}" />
<!-- Binds button to the ItalicCommand -->
<Button Content="Italic" Command="{Binding ElementName=richTextBoxAdv, Path=ItalicCommand, Mode=TwoWay}" />


{% endhighlight %}

{% endtabs %}
