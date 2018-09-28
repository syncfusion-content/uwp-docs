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

* Table – Insert table, Insert row, Insert column, Delete table, Delete row, Delete column and Merge selected cells, Select cell, Select column, Select row, Select table and Align cell content.

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

{% highlight c# %}
/// <summary>
/// Apply bold style for the selected contents of SfRichTextBoxAdv.
/// </summary>
public void Bold()
{
    // Executes bold command.
    if (richTextBoxAdv.BoldCommand.CanExecute(null))
        richTextBoxAdv.BoldCommand.Execute(null);
}
/// <summary>
/// Apply itaic style for the selected contents of SfRichTextBoxAdv.
/// </summary>
public void Italic()
{
    // Executes copy command.
    if (richTextBoxAdv.ItalicCommand.CanExecute(null))
        richTextBoxAdv.ItalicCommand.Execute(null);
}
{% endhighlight %}
{% endtabs %}

## List of available Commands

The following table contains the list of available UI Commands in SfRichTextBoxAdv.

<table>
<thead>
<th>
<p>Command Name</p>
</th>
<th>
<p>Description</p>
</th>
<th>
<p>Command parameter (optional)</p>
</th>
</thead>
<tbody>
<tr>
<td>
<p>AddToDictionaryCommand</p>
</td>
<td>
<p>Represents the command to add the selected or specified custom word into the custom dictionary.</p>
</td>
<td>
<p>The custom word to add into dictionary.</p>
</td>
</tr>
<tr>
<td>
<p>AfterSpacingCommand</p>
</td>
<td>
<p>Represents the command to change the after spacing for the selected paragraphs.</p>
</td>
<td>
<p>The after spacing value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>AutoFitTableCommand</p>
</td>
<td>
<p>Represents the command to fits the columns width of selected table in `SfRichTextBoxAdv` control based on type `AutoFitType`.</p>
</td>
<td>
<p>The `AutoFitType` to fit the columns of the table.</p>
</td>
</tr>
<tr>
<td>
<p>BaselineAlignmentCommand</p>
</td>
<td>
<p>Represents the command to change `BaselineAlignment` for the selected text.</p>
</td>
<td>
<p>The baseline alignment value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>BeforeSpacingCommand</p>
</td>
<td>
<p>Represents the command to change the before spacing for the selected paragraphs.</p>
</td>
<td>
<p>The before spacing value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>BoldCommand</p>
</td>
<td>
<p>Represents the command to toggle the bold style for the selected text.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>CellBottomMarginCommand</p>
</td>
<td>
<p>Represents the command to change bottom margin for the selected table cell.</p>
</td>
<td>
<p>The bottom margin value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>CellContentAlignmentCommand</p>
</td>
<td>
<p>Represents the command to apply content alignment for the selected table cells .</p>
</td>
<td>
<p>The cell content alignment value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>CellLeftMarginCommand</p>
</td>
<td>
<p>Represents the command to change left margin for the selected table cell.</p>
</td>
<td>
<p>The left margin value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>CellRightMarginCommand</p>
</td>
<td>
<p>Represents the command to change the value of right margin for the selected table cell.</p>
</td>
<td>
<p>The right margin value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>CellSpacingCommand</p>
</td>
<td>
<p>Represents the command to apply cell spacing for the selected table.</p>
</td>
<td>
<p>The cell spacing value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>CellTopMarginCommand</p>
</td>
<td>
<p>Represents the command to apply top margin for the selected table cell.</p>
</td>
<td>
<p>The top margin value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>CellVerticalAlignmentCommand</p>
</td>
<td>
<p>Represents the command to apply vertical alignment for the selected cell.</p>
</td>
<td>
<p>The vertical alignment value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>ChangeAllSpellingCommand</p>
</td>
<td>
<p>Represents the command that changes all occurrences of a selected misspelled word.</p>
</td>
<td>
<p>The word to be replaced.</p>
</td>
</tr>
<tr>
<td>
<p>ChangeSpellingCommand</p>
</td>
<td>
<p>Represents the command that changes the selected misspelled word.</p>
</td>
<td>
<p>The word to be replaced.</p>
</td>
</tr>
<tr>
<td>
<p>CheckSpellingCommand</p>
</td>
<td>
<p>Represents the command that checks spelling mistakes in the document of `SfRichTextBoxAdv` control.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>CopyCommand</p>
</td>
<td>
<p>Represents the command that copies the selected contents to clipboard.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>CutCommand</p>
</td>
<td>
<p>Represents the command that removes selected contents from `SfRichTextBoxAdv` control and copies the same to clipboard.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>DecreaseIndentCommand</p>
</td>
<td>
<p>Represents the command to decrease the left indent for the selected paragraphs.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>DefaultCellBottomMarginCommand</p>
</td>
<td>
<p>Represents the command to apply bottom margin for the selected table.</p>
</td>
<td>
<p>The cell bottom margin value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>DefaultCellLeftMarginCommand</p>
</td>
<td>
<p>Represents the command to apply left margin for the selected table.</p>
</td>
<td>
<p>The cell left margin value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>DefaultCellRightMarginCommand</p>
</td>
<td>
<p>Represents the command to apply right margin for the selected table.</p>
</td>
<td>
<p>The cell right margin value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>DefaultCellTopMarginCommand</p>
</td>
<td>
<p>Represents the command to apply top margin for the selected table.</p>
</td>
<td>
<p>The cell top margin value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>DeleteAllCommentsCommand</p>
</td>
<td>
<p>Represents the command that to delete all comments in the document.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>DeleteColumnCommand</p>
</td>
<td>
<p>Represents the command that to delete the selected column of a table.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>DeleteCommentCommand</p>
</td>
<td>
<p>Represents the command that any comment at the current position be deleted.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>DeleteRowCommand</p>
</td>
<td>
<p>Represents the command that delete the selected row of a table.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>DeleteTableCommand</p>
</td>
<td>
<p>Represents the command that delete the selected table.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<td>
<p>EnterKeyCommand</p>
</td>
<td>
<p>Represents the command that perform action for "ENTER" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>FontColorCommand</p>
</td>
<td>
<p>Represents the command that apply font color for the selected text.</p>
</td>
<td>
<p>The font color value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>FontFamilyCommand</p>
</td>
<td>
<p>Represents the command that apply font family for the selected text.</p>
</td>
<td>
<p>The font family value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>FontSizeCommand</p>
</td>
<td>
<p>Represents the command that apply font size for the selected text.</p>
</td>
<td>
<p>The font size value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>HighlightColorCommand</p>
</td>
<td>
<p>Represents the command that apply `HighlightColor` for the selected text.</p>
</td>
<td>
<p>The highlight color value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>IgnoreAllSpellingErrorsCommand</p>
</td>
<td>
<p>Represents the command that that all occurrences of any misspelled word at the current position be ignored.</p>
</td>
<td>
<p>The misspelled word to be ignored.</p>
</td>
</tr>
<tr>
<td>
<p>IncreaseIndentCommand</p>
</td>
<td>
<p>Represents the command that increase indent for the selected paragraphs.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>InsertBreakCommand</p>
</td>
<td>
<p>Represents the command that inserts a break at current position.</p>
</td>
<td>
<p>The break type to be inserted</p>
</td>
</tr>
<tr>
<td>
<p>InsertColumnCommand</p>
</td>
<td>
<p>Represents the command that insert a column at current position.</p>
</td>
<td>
<p>The `ColumnPlacement` value to insert column.</p>
</td>
</tr>
<tr>
<td>
<p>InsertHyperlinkCommand</p>
</td>
<td>
<p>Represents the command that inserts a hyperlink at current position.</p>
</td>
<td>
<p>The hyperlink to be inserted.</p>
</td>
</tr>
<tr>
<td>
<p>InsertPictureCommand</p>
</td>
<td>
<p>Represents the command that inserts a picture at current position.</p>
</td>
<td>
<p>The picture to be inserted.</p>
</td>
</tr>
<tr>
<td>
<p>InsertRowCommand</p>
</td>
<td>
<p>Represents the command that insert a row at current position in `SfRichTextBoxAdv` control.</p>
</td>
<td>
<p>The `RowPlacement` value to insert row.</p>
</td>
</tr>
<tr>
<td>
<p>InsertTableCommand</p>
</td>
<td>
<p>Represents the command that inserts a table at current position.</p>
</td>
<td>
<p>The row and column count to insert.</p>
</td>
</tr>
<tr>
<td>
<p>ItalicCommand</p>
</td>
<td>
<p>Represents the command that toggle the italic format for the selected text.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>LayoutTypeCommand</p>
</td>
<td>
<p>Represents the command that the change the layout type of `SfRichTextBoxAdv` control.</p>
</td>
<td>
<p>The layout type to be set for SfRichTextBoxAdv.</p>
</td>
</tr>
<tr>
<td>
<p>LeftIndentCommand</p>
</td>
<td>
<p>Represents the command that apply left indent for the selected paragraphs.</p>
</td>
<td>
<p>The left indent value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>LineSpacingCommand</p>
</td>
<td>
<p>Represents the command that apply line spacing for the selected paragraphs.</p>
</td>
<td>
<p>The line spacing value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>LineSpacingTypeCommand</p>
</td>
<td>
<p>Represents the command that apply `LineSpacingType` for the selected paragraphs.</p>
</td>
<td>
<p>The line spacing type value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>MergeSelectedCellsCommand</p>
</td>
<td>
<p>Represents the command that merge the currently selected cells.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>NewCommentCommand</p>
</td>
<td>
<p>Represents the command that adds a comment at the current position.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>NewDocumentCommand</p>
</td>
<td>
<p>Represents the command that creates a new document in `SfRichTextBoxAdv` control.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>NextCommentCommand</p>
</td>
<td>
<p>Represents the command that perform navigation to any next comment in the document.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>OpenDocumentCommand</p>
</td>
<td>
<p>Represents the command that open an existing document in to `SfRichTextBoxAdv` control.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>PageFitCommand</p>
</td>
<td>
<p>Represents the command that the changes `PageFitType` in `SfRichTextBoxAdv` control.</p>
</td>
<td>
<p>The `PageFitType` value for the document in pages view.</p>
</td>
</tr>
<tr>
<td>
<p>PasteAsyncCommand </p>
</td>
<td>
<p>Represents the command that paste the clipboard contents into `SfRichTextBoxAdv` control asynchronously .</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>PasteCommand</p>
</td>
<td>
<p>Represents the command that paste the clipboard contents into `SfRichTextBoxAdv` control.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>PreviousCommentCommand</p>
</td>
<td>
<p>Represents the command that perform navigation to any previous comment in the document.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>PrintDocumentCommand</p>
</td>
<td>
<p>Represents the command that print the document in `SfRichTextBoxAdv` control.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>RedoCommand</p>
</td>
<td>
<p>Represents the command that the last undone operation in `SfRichTextBoxAdv` control be redone.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>RightIndentCommand</p>
</td>
<td>
<p>Represents the command that apply right indent for the selected paragraphs.</p>
</td>
<td>
<p>The right indent value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>SaveAsDocumentCommand</p>
</td>
<td>
<p>Represents the command that save the document in `SfRichTextBoxAdv` control.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>SaveDocumentCommand</p>
</td>
<td>
<p>Represents the command that save the document in `SfRichTextBoxAdv` control.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>SelectAllCommand</p>
</td>
<td>
<p>Represents the command that selects all the content in `SfRichTextBoxAdv`.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>SelectCellCommand</p>
</td>
<td>
<p>Represents the command that selects the current table cell.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>SelectColumnCommand</p>
</td>
<td>
<p>Represents the command that selects the entire current column from a table in `SfRichTextBoxAdv`.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>SelectRowCommand</p>
</td>
<td>
<p>Represents the command that selects the entire current row from a table.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>SelectTableCommand</p>
</td>
<td>
<p>Represents the command that selects the current table.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ShowCommentsCommand</p>
</td>
<td>
<p>Represents the command that shows the comments in `SfRichTextBoxAdv` control.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ShowHyperlinkDialogCommand</p>
</td>
<td>
<p>Represents the command that shows the hyperlink dialog.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ShowOptionsPaneCommand</p>
</td>
<td>
<p>Represents the command that shows the options pane.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ShowSpellingPaneCommand</p>
</td>
<td>
<p>Represents the command that shows the spelling pane.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>StrikeThroughCommand</p>
</td>
<td>
<p>Represents the command that apply `StrikeThrough` for the selected text in `SfRichTextBoxAdv` control.</p>
</td>
<td>
<p>The strike through value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>TableAlignmentCommand</p>
</td>
<td>
<p>Represents the command that apply table alignment for the selected table.</p>
</td>
<td>
<p>The table alignment value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>TableLeftIndentCommand</p>
</td>
<td>
<p>Represents the command that apply left indent for the selected table.</p>
</td>
<td>
<p>The left indent value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>TextAlignmentCommand</p>
</td>
<td>
<p>Represents the command that apply text alignment for the selected paragraphs.</p>
</td>
<td>
<p>The text alignment value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>UnderlineCommand</p>
</td>
<td>
<p>Represents the command that apply underline for the selected text.</p>
</td>
<td>
<p>The `Underline` value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>UndoCommand</p>
</td>
<td>
<p>Represents the command that the last edit operation in `SfRichTextBoxAdv` control be undone.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
</tbody>
</table>