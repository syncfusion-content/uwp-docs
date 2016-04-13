---
layout: post
title: Interactive Features of SfSpreadsheet
description: How to use the clipboard operations, undo/redo and other functionalities in SfSpreadsheet
platform: UWP
control: SfSpreadsheet
documentation: ug
---

# Interactive Features

 This section explains about the interactive operations with SfSpreadsheet
 
## Clipboard Operations

SfSpreadsheet provides support for all the clipboard operations to with all the format settings when copied within a workbook.  

You can use the following shortcut keys for Clipboard operations like Excel
<table>
<tr>
<th>
Operations</th><th>
Shortcut Keys</th></tr>
<tr>
<td>
Cut</td><td>
Ctrl + X</td></tr>
<tr>
<td>
Copy</td><td>
Ctrl + C </td></tr>
<tr>
<td>
Paste</td><td>
Ctrl + V</td></tr>
</table>

The following are a list of paste options used while performing paste operation,

<table>
<tr>
<th>
Options</th><th>
Description</th></tr>
<tr>
<td>
Paste</td><td>
To paste with all the format options in the source range</td></tr>
<tr>
<td>
Formula</td><td>
To paste the formulas alone </td></tr>
<tr>
<td>
Keep Source Formatting</td><td>
To maintain the source range’s formatting</td></tr>
<tr>
<td>
Value</td><td>
To paste the values alone</td></tr>
<tr>
<td>
Format</td><td>
To paste only the formats alone without pasting the values.</td></tr>
<tr>
<td>
Value & Source Formatting</td><td>
To maintain the source range original format and paste only values</td></tr>
</table>

For `Cut` Operation,

{% tabs %}
{% highlight c# %}
			
//To perform cut operation for selected ranges

var range = spreadsheet.ActiveGrid.SelectedRanges.ActiveRange;

spreadsheet.ActiveGrid.CopyPaste.Copy(range, true);

//To perform cut operation

spreadsheet.ActiveGrid.CopyPaste.Cut();

{% endhighlight %}
{% endtabs %}

For `Copy` Operation,

{% tabs %}
{% highlight c# %}

//To perform copy operation for selected ranges

var range = spreadsheet.ActiveGrid.SelectedRanges.ActiveRange;

 spreadsheet.ActiveGrid.CopyPaste.Copy(range, false);

//To perform Copy operation

spreadsheet.ActiveGrid.CopyPaste.Copy();

{% endhighlight %}
{% endtabs %}

For `Paste` Operation,

{% tabs %}
{% highlight c# %}

//To perform paste operation

spreadsheet.ActiveGrid.CopyPaste.Paste();

//To perform paste operation with range and Paste Options

var copyPaste = spreadsheet.ActiveGrid.CopyPaste as SpreadsheetCopyPaste;

copyPaste.Paste(range);

copyPaste.Paste(range, PasteOptions.Paste);

{% endhighlight %}
{% endtabs %}

N> When the content is copied from external source, SfSpreadsheet does not support the format settings (paste options).


## Undo/Redo

SfSpreadsheet provides support for Undo/Redo functionality like MS Excel.

The shortcut keys used for Undo/Redo Operations

<table>
<tr>
<th>
Operations</th><th>
Shortcut Keys</th></tr>
<tr>
<td>
Undo</td><td>
Ctrl + Z</td></tr>
<tr>
<td>
Redo</td><td>
Ctrl + Y</td></tr>
</table>

SfSpreadsheet has `History Manager` class that supports the implementation of undo/ redo operations

To invoke Undo/Redo operations, the `Enabled` property of `History Manager` needs to be true.  

{% tabs %}
{% highlight c# %}

spreadsheet.HistoryManager.Enabled = true;

spreadsheet.HistoryManager.Undo();

spreadsheet.HistoryManager.Redo();

{% endhighlight %}
{% endtabs %}


## Context menu

Context menu in SfSpreadsheet is customizable menu which can be used for various functionalities


### Cell Context menu

By default, `AllowCellContextMenu` property is set as true to enable the CellContext Menu in SfSpreadsheet. The Event associated with Cell Context menu `CellContextMenuOpening` Event of SpreadsheetGrid.

Adding the customized menu items in the CellContextMenuOpening Event,

{% tabs %}
{% highlight c# %}

spreadsheet.ActiveGrid.CellContextMenuOpening += ActiveGrid_CellContextMenuOpening;

void ActiveGrid_CellContextMenuOpening(object sender, CellContextMenuOpeningEventArgs e)
{
    //Adding Customized Menu item
        
    MenuItem PasteSpecial = new MenuItem();
    PasteSpecial.Header = "Pastespecial";
    Image paste = new Image() { Source = new BitmapImage(new Uri(@"..\..\Icon\paste.png", UriKind.Relative)) };
    PasteSpecial.Icon = paste;
    spreadsheet.ActiveGrid.CellContextMenu.Items.Add(PasteSpecial);
        
    //Remove the existing Context menu
    spreadsheet.ActiveGrid.CellContextMenu.Items.RemoveAt(2);
}
    
{% endhighlight %}
{% endtabs %}


## Cell Comments

SfSpreadsheet provides support for cell comments like in excel to give the reader additional context for the data it contains. You can set the comment height and color for the particular comments at runtime by invoking `CellCommentOpening` Event of SpreadsheetGrid

To enable the comment in SfSpreadsheet, set the `ShowComment` property of SpreadsheetGrid to true.


{% tabs %}
{% highlight c# %}

    spreadsheet.ActiveGrid.ShowComment = true;

{% endhighlight %}
{% endtabs %}

To set the comments for particular cell at run time,

{% tabs %}
{% highlight c# %}

spreadsheet.ActiveSheet.Range["E5"].AddComment().Text = "Sample Comment";
spreadsheet.ActiveGrid.InvalidateCell(5, 5);
	
{% endhighlight %}
{% endtabs %}

