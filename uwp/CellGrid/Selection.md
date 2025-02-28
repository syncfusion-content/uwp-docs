---
layout: post
title: Selection in UWP CellGrid control | Syncfusion®
description: Learn here all about Selection support in Syncfusion® UWP CellGrid (SfCellGrid) control and more.
platform: UWP
control: SfCellGrid
documentation: ug
---

# Selection in UWP CellGrid (SfCellGrid)

This section explains about the Selection behavior in SfCellGrid.

The SfCellGrid control provides support for selection in grid by using mouse, keyboard and touch interactions.

By default, Selection behavior will be enabled in SfCellGrid, but if you want to disable the selection in SfCellGrid, then set the `AllowSelection` Property to be false.

{% tabs %}
{% highlight c# %}

    cellGrid.AllowSelection = false;

{% endhighlight %}
{% endtabs %}

## Accessing the Current cell

SfCellGrid allows the user to access the active cell by using the `CurrentCell` property of `SelectionController` Class.

{% tabs %}
{% highlight c# %}

var cell = cellGrid.SelectionController.CurrentCell;

{% endhighlight %}
{% endtabs %}

## Accessing the Selected ranges

SfCellGrid allows the user to access the selected ranges list using the `SelectedRanges` property.

{% tabs %}
{% highlight c# %}

var rangeList = cellGrid.SelectedRanges;

{% endhighlight %}
{% endtabs %}

N> To get the active range in the selected ranges list, use `ActiveRange` property of `GridRangeInfoList` class.

## Adding or Clearing the Selection

SfCellGrid allows the user to add and clear the selection for the given range.

{% tabs %}
{% highlight c# %}

//To Add the Selection for range,
cellGrid.SelectionController. AddSelection(GridRangeInfo.Cells(4,6,5,8));

//To Add the Selection for row,
cellGrid.SelectionController.AddSelection(GridRangeInfo.Row(4));

//To Add the Selection for multiple rows,
cellGrid.SelectionController. AddSelection(GridRangeInfo.Rows(4,9));

//To Add the Selection for column,
cellGrid.SelectionController.AddSelection(GridRangeInfo.Col(5));

//To Add the Selection for multiple columns,
cellGrid.SelectionController. AddSelection(GridRangeInfo.Cols(5,10));

//To Clear the Selection,
cellGrid.SelectionController.ClearSelection();

{% endhighlight %}
{% endtabs %}

## Move Current Cell

SfCellGrid allows the user to move the current cell to the mentioned cell.

{% tabs %}
{% highlight c# %}

//Moves current cell to the mentioned row and column index of cell,
cellGrid.CurrentCell.MoveCurrentCell(5, 5);

{% endhighlight %}
{% endtabs %}

## Selection Attributes

### SelectionBorderThickness

SfCellGrid allows the user to set the thickness of the border around the selected cells.

{% tabs %}
{% highlight c# %}

cellGrid.SelectionBorderThickness = 5;

{% endhighlight %}
{% endtabs %}

### SelectionBorderBrush
 
SfCellGrid allows the user to set the brush color of the border around the selected cells.

{% tabs %}
{% highlight c# %} 

cellGrid.SelectionBorderBrush = new SolidColorBrush(Colors.DarkOliveGreen);

{% endhighlight %}
{% endtabs %}

### SelectionBrush

SfCellGrid allows the user to set the brush color for background of the selected cells.

{% tabs %}
{% highlight c# %} 

cellGrid.SelectionBrush = new SolidColorBrush(Colors.Red);
            
{% endhighlight %}
{% endtabs %}

## Properties, Methods and Events

Below table lists the events associated with selection behavior,

<table>
<tr>
<th>
Events</th><th>
Description</th></tr>
<tr>
<td>
<code>CellClick</code></td><td>
 Occurs when you click on the cell. </td></tr>
<tr>
<td>
<code>CurrentCellActivating</code></td><td>
Occurs when the current cell is going to be activated. This event allows to cancel the current cell activation. </td></tr>
<tr>
<td>
<code>CurrentCellActivated</code></td><td>
Occurs after the current cell is activated. </td></tr>
<tr>
<td>
<code>SelectionChanging</code></td><td>
Occurs when the selection is going to be changed. This event allows to cancel the selection change. </td></tr>
<tr>
<td>
<code>SelectionChanged</code></td><td>
Occurs after the selection is changed. </td></tr>
</table>

Below table lists the properties associated with selection,

<table>
<tr>
<th>
Properties</th><th>
Description</th></tr>
<tr>
<td>
<code>SelectedRanges</code></td><td>
Gets or sets the collection of selected ranges from grid. </td></tr>
<tr>
<td>
<code>SelectionBrush</code></td><td>
Gets or sets the selected area brush. </td></tr>
<tr>
<td>
<code>SelectionBorderBrush</code></td><td>
Gets or sets the selection border brush. </td></tr>
<tr>
<td>
<code>SelectionBorderThickness</code></td><td>
Gets or sets the thickness of selection border. </td></tr>
<tr>
<td>
<code>SelectionController</code></td><td>
 Gets the Selection Controller which provides the selection of content when the user drags the pressed mouse to an edge of the control. </td></tr>
<tr>
<td>
<code>AllowSelection</code></td><td>
Gets or Sets the value whether to allow the selection in the SfCellGrid or not. </td></tr>
<tr>
<td>
<code>ShowTouchIndicator</code></td><td>
Determines whether the touch indicator will be shown or not. </td></tr>
<tr>
<td>
<code>TouchHitTestPrecision</code></td><td>
Gets or sets the distance of touch precision point from touch indicator. </td></tr>
</table>
 
Below table lists the properties associated with `CurrentCell` ,

<table>
<tr>
<th>
Properties</th><th>
Description</th></tr>
<tr>
<td>
<code>CellRowColumnIndex</code></td><td>
Gets the row and column index of the Current Cell. </td></tr>
<tr>
<td>
<code>RowIndex</code></td><td>
Gets the row index of the Current Cell. </td></tr>
<tr>
<td>
<code>ColumnIndex</code></td><td>
Gets the column index of the Current Cell. </td></tr>
<tr>
<td>
<code>Range</code></td><td>
Gets the range of the Current Cell. </td></tr>
<tr>
<td>
<code>HasCurrentCell</code></td><td>
Gets the value indicating whether the Grid has Current Cell or not. </td></tr>
<tr>
<td>
<code>PreviousRowColumnIndex</code></td><td>
Gets or sets the row and column index of old Current Cell. </td></tr>
</table>

Below table lists the methods associated with selection,

<table>
<tr>
<th>
Methods</th><th>
Description</th></tr>
<tr>
<td>
<code>AddSelection</code></td><td>
Adds/Extends the Selection to the mentioned range. </td></tr>
<tr>
<td>
<code>ClearSelection</code></td><td>
Clears the Selection. </td></tr>
<tr>
<td>
<code>MoveCurrentCell</code></td><td>
Move the Current cell to mentioned row and column index. </td></tr>
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
Moves to the first cell of the current row. </td></tr>
<tr>
<td>
END</td><td>
Moves to the last cell of the current row. </td></tr>
<tr>
<td>
UPARROW
</td><td>
Moves to one cell up of the current cell in the SfCellGrid. </td></tr>
<tr>
<td>
DOWNARROW
</td><td>
Moves to one cell down of the current cell in the SfCellGrid. </td></tr>
<tr>
<td>
LEFTARROW
</td><td>
Moves to one cell left of the current cell in the SfCellGrid. </td></tr>
<tr>
<td>
RIGHTARROW
</td><td>
Moves to one cell right of the current cell in the SfCellGrid. </td></tr>
<tr>
<td>
PAGEUP</td><td>
Moves to the first visible cell of the current column. </td></tr>
<tr>
<td>
PAGEDOWN</td><td>
Moves to the last visible cell of the current column. </td></tr>
<tr>
<td>
CTRL+HOME</td><td>
Moves to the beginning cell of a SfCellGrid. </td></tr>
<tr>
<td>
CTRL+END</td><td>
Moves to the last cell of a SfCellGrid. </td></tr>
<tr>
<td>
ALT+PAGE UP</td><td>
Moves one screen to the left in a SfCellGrid. </td></tr>
<tr>
<td>
ALT+PAGE DOWN</td><td>
Moves one screen to the right in a SfCellGrid. </td></tr>
<tr>
<td>
CTRL + ARROW KEYS</td><td>
Moves to the first/last cell of the current cell based on Arrow directions. </td></tr>
<tr>
<td>
ENTER</td><td>
Moves the active current cell to one cell down in the selection. </td></tr>
<tr>
<td>
SHIFT+ENTER</td><td>
Moves the active current cell to one cell up in the selection. </td></tr>
<tr>
<td>
TAB</td><td>
Moves the active current cell in one cell to the right of the selection. </td></tr>
<tr>
<td>
SHIFT+TAB</td><td>
Moves the active current cell in one cell to the left of the selection. </td></tr>
<tr>
<td>
BACKSPACE</td><td>
Begins the edit operation for the active cell in the selection. </td></tr>
<tr>
<td>
CTRL+A</td><td>
Selects the entire worksheet. </td></tr>
<tr>
<td>
SHIFT+ARROW KEYS</td><td>
Extends the selection by one cell based on the arrow direction. </td></tr>
<tr>
<td>
CTRL+SHIFT+ARROW KEYS</td><td>
Extend the selection to the last cell in a row or column. </td></tr>
<tr>
<td>
SHIFT+HOME</td><td>
Extends the selection to the first column from the active cell. </td></tr>
<tr>
<td>
CTRL+SHIFT+HOME</td><td>
Extends the selection from the active cell to the first cell. </td></tr>
<tr>
<td>
SHIFT+PAGE DOWN</td><td>
Extends the selection down in a SfCellGrid. </td></tr>
<tr>
<td>
SHIFT+PAGE UP</td><td>
Extends the selection up in a SfCellGrid. </td></tr>
</table>

## Touch Selection Attributes

SfCellGrid provides support for touch selection. 

### ShowTouchIndicator

By default, the touch indicator is enabled in SfCellGrid. If you want to disable the indicator, then set the `ShowTouchIndicator` to false.

{% tabs %}
{% highlight c# %} 

cellGrid.SelectionController.ShowTouchIndicator = false;

{% endhighlight %}
{% endtabs %}

### TouchHitTestPrecision

`TouchHitTestPrecision` property sets the distance of touch precision point from touch indicator. By default, it`s value is 10.

{% tabs %}
{% highlight c# %} 

var point = cellGrid.SelectionController.TouchHitTestPrecision;

{% endhighlight %}
{% endtabs %}
