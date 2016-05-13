---
layout: post
title: Selection behavior in SfSpreadsheet 
description: selection behavior of SfSpreadsheet
platform: UWP
control: SfSpreadsheet
documentation: ug
---

# Selection

This section explains about the Selection behavior in SfSpreadsheet.

The SfSpreadsheet control provides support for selection in grid by using mouse, keyboard and touch interactions.

By default, Selection behavior will be enabled in `SfSpreadsheet`,but if you want to disable the selection in SfSpreadsheet, then set the `AllowSelection` Property to be false.

{% tabs %}
{% highlight c# %}

void spreadsheet_WorkbookLoaded(object sender, WorkbookLoadedEventArgs args)
{
    spreadsheet.ActiveGrid.AllowSelection = false;
}

{% endhighlight %}
{% endtabs %}

## Accessing the Current cell

SfSpreadsheet allows the user to access the active cell by using the `CurrentCell` property of `SelectionController` Class.

{% tabs %}
{% highlight c# %}

var cell= spreadsheet.ActiveGrid.SelectionController.CurrentCell;

{% endhighlight %}
{% endtabs %}

## Accessing the Selected ranges

SfSpreadsheet allows the user to access the selected ranges of the `SpreadsheetGrid` using `SelectedRanges` property of `SpreadsheetGrid`.

{% tabs %}
{% highlight c# %}

var rangelist = spreadsheet.ActiveGrid.SelectedRanges;

{% endhighlight %}
{% endtabs %}

N> To get the active range in the selected ranges list, use `ActiveRange` property of `GridRangeInfoList` class.

## Adding or Clearing the Selection

SfSpreadsheet allows the user to add and clear the selection in the Active `SpreadsheetGrid` for the given range.

{% tabs %}
{% highlight c# %}

//To Add the Selection for the given range,
spreadsheet.ActiveGrid.SelectionController.AddSelection(GridRangeInfo.Cells(4,6,5,8));

//To Clear the Selection,
spreadsheet.ActiveGrid.SelectionController.ClearSelection();

{% endhighlight %}
{% endtabs %}

## Converting GridRangeInfo into IRange

SfSpreadsheet allows the user to convert the `GridRangeInfo` into the equivalent `IRange` by using `ConvertGridRangeToExcelRange` method of `GridExcelHelper` class.

{% tabs %}
{% highlight c# %}

var excelrange = GridExcelHelper.ConvertGridRangeToExcelRange(GridRangeInfo.Cell(4, 5), spreadsheet.ActiveGrid);

{% endhighlight %}
{% endtabs %}

T> Users can also convert the `IRange` into equivalent `GridRangeInfo` by using `ConvertExcelRangeToGridRange` method of  `GridExcelHelper` class.

## Properties, Methods and Events

Below table lists the events associated with selection behavior,

<table>
<tr>
<th>
Events</th><th>
Description</th></tr>
<tr>
<td>
<B>CellClick</B></td><td>
 Occurs when you click on the cell.</td></tr>
<tr>
<td>
<B>CurrentCellActivating</B></td><td>
Occurs when the current cell is going to be activated. This event allow to cancel the current cell activation.</td></tr>
<tr>
<td>
<B>CurrentCellActivated</B></td><td>
Occurs after the current cell is activated.</td></tr>
<tr>
<td>
<B>SelectionChanging</B></td><td>
Occurs when the selection is going to be changed. This event allows to cancel the selection change.</td></tr>
<tr>
<td>
<B>SelectionChanged</B></td><td>
Occurs after the selection is changed.</td></tr>
</table>

Below table lists the properties associated with selection,

<table>
<tr>
<th>
Properties</th><th>
Description</th></tr>
<tr>
<td>
<B>SelectedRanges</B></td><td>
Gets or sets the collection of selected ranges from grid.</td></tr>
<tr>
<td>
<B>SelectionBrush</B></td><td>
Gets or sets the selected area brush.</td></tr>
<tr>
<td>
<B>SelectionBorderBrush</B></td><td>
Gets or sets the selection border brush.</td></tr>
<tr>
<td>
<B>SelectionBorderThickness</B></td><td>
Gets or sets the thickness of selection border.</td></tr>
<tr>
<td>
<B>SelectionController</B></td><td>
 Gets the Selection Controller which provides the selection of content when the user drags the pressed mouse to an edge of the control.</td></tr>
<tr>
<td>
<B>AllowSelection</B></td><td>
 Gets or Sets the value whether to allow the selection in the ActiveGrid or not.</td></tr>
 </table>
 
Below table lists the properties associated with `CurrentCell` of `SpreadsheetGrid`,

<table>
<tr>
<th>
Properties</th><th>
Description</th></tr>
<tr>
<td>
<B>CellRowColumnIndex</B></td><td>
Gets the row and column index of the CurrentCell.</td></tr
<tr>
<td>
<B>RowIndex</B></td><td>
Gets the row index of the CurrentCell.</td></tr>
<tr>
<td>
<B>ColumnIndex</B></td><td>
Gets the column index of the CurrentCell.</td></tr>
<tr>
<td>
<B>Range</B></td><td>
Gets the range of the CurrentCell.</td></tr>
<tr>
<td>
<B>HasCurrentCell</B></td><td>
 Gets the value indicating whether the Grid has CurrentCell or not.</td></tr>
 <tr>
 <td>
 <B>PreviousRowColumnIndex</B></td><td>
 Gets or sets the row and column index of old CurrentCell.</td></tr>
</table>

Below table lists the methods associated with selection,

<table>
<tr>
<th>
Methods</th><th>
Description</th></tr>
<tr>
<td>
<B>AddSelection</B></td><td>
Adds/Extends the Selection to the mentioned range .</td></tr>
<tr>
<td>
<B>ClearSelection</B></td><td>
Clears the Selection.</td></tr>
<tr>
<td>
<B>MoveCurrentCell</B></td><td>
Move the Currentcell to mentioned row and column index.</td></tr>
</table>

## Key Navigation

Below table lists the key combinations associated with selection,

<table>
<tr>
<th>
Key Combination</th><th>
Description</th></tr>
<tr>
<td>
HOME</td><td>
Moves to the first cell of the current row .</td></tr>
<tr>
<td>
END</td><td>
Moves to the last cell of the current row .</td></tr>
<tr>
<td>
UPARROW
</td><td>
Moves to one cell up of the current cell in the worksheet.</td></tr>
<tr>
<td>
DOWNARROW
</td><td>
Moves to one cell down of the current cell in the worksheet.</td></tr>
<tr>
<td>
LEFTARROW
</td><td>
Moves to one cell left of the current cell in the worksheet.</td></tr>
<tr>
<td>
RIGHTARROW
</td><td>
Moves to one cell right of the current cell in the worksheet.</td></tr>
<tr>
<td>
PAGEUP</td><td>
Moves to the first visible cell of the current column.</td></tr>
<tr>
<td>
PAGEDOWN</td><td>
Moves to the last visible cell of the current column.</td></tr>
<tr>
<td>
CTRL+HOME</td><td>
Moves to the beginning cell of a worksheet.</td></tr>
<tr>
<td>
CTRL+END</td><td>
Moves to the last cell of a worksheet.</td></tr>
<tr>
<td>
ALT+PAGE UP</td><td>
Moves one screen to the left in a worksheet.</td></tr>
<tr>
<td>
ALT+PAGE DOWN</td><td>
Moves one screen to the right in a worksheet.</td></tr>
<tr>
<td>
CTRL + ARROW KEYS</td><td>
Moves to the  first/last cell of the current cell based on Arrow directions .</td></tr>
<tr>
<td>
ENTER</td><td>
Moves the active current cell to one cell down in the selection.</td></tr>
<tr>
<td>
SHIFT+ENTER</td><td>
Moves the active current cell to one cell up in the selection.</td></tr>
<tr>
<td>
TAB</td><td>
Moves the active current cell in one cell to the right of the selection.</td></tr>
<tr>
<td>
SHIFT+TAB</td><td>
Moves the active current cell in  one cell to the left of the selection.</td></tr>
<tr>
<td>
BACKSPACE</td><td>
Begins the edit operation for the active cell in the selection.</td></tr>
<tr>
<td>
CTRL+A</td><td>
Selects the entire worksheet.</td></tr>
<tr>
<td>
SHIFT+ARROW KEYS</td><td>
Extends the selection by one cell based on the arrow direction.</td></tr>
<tr>
<td>
CTRL+SHIFT+ARROW KEYS</td><td>
Extend the selection to the last cell in a row or column.</td></tr>
<tr>
<td>
SHIFT+HOME</td><td>
Extends the selection to the first column from the active cell.</td></tr>
<tr>
<td>
CTRL+SHIFT+HOME</td><td>
Extends the selection from the active cell to the first cell.</td></tr>
<tr>
<td>
SHIFT+PAGE DOWN</td><td>
Extends the selection down in a worksheet.</td></tr>
<tr>
<td>
SHIFT+PAGE UP</td><td>
Extends the selection up in a worksheet.</td></tr>
</table>





