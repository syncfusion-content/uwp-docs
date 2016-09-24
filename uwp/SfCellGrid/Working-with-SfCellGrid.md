---
layout: post
title: Working with SfCellGrid 
description: How to work with CellGrid and its properties
platform: uwp
control: SfCellGrid
documentation: ug
---

# Working with CellGrid
 This section explains about the virtualization behavior, programmatic scrolling and refreshing the grid.

## Virtualization

SfCellGrid provides support for virtualization which lets you to provide the data dynamically to grid through QueryCellInfo Event.
SfCellGrid does not store the cell data in GridStyleInfo objects or any other internal grid storage while populating the data through this event, 
thus increasing the performance. 

This event is used to provide GridStyleInfo object for a given cell. The CellValue property of the GridStyleInfo object holds the data. 
All the changes made in this event is done in on-demand basis and not stored in any internal storage.

{% tabs %}
{% highlight c# %}

// Loading one million rows and ten thousand columns ,

cellGrid.RowCount = 1000000; 

cellGrid.ColumnCount = 10000;

cellGrid.Model.QueryCellInfo += Model_QueryCellInfo;

//Assigning values by handling the QueryCellInfo event

private void Model_QueryCellInfo(object sender, Syncfusion.UI.Xaml.CellGrid.Styles.GridQueryCellInfoEventArgs e)
{
    if (e.Cell.RowIndex == 0 && e.Cell.ColumnIndex == 0)
       return;
    if (e.Cell.RowIndex == 0)
    {
       e.Style.CellValue = e.Cell.ColumnIndex;
       e.Style.Font.FontWeight = Windows.UI.Text.FontWeights.Bold;
	   e.Style.VerticalAlignment = VerticalAlignment.Center;
	   e.Style.HorizontalAlignment = HorizontalAlignment.Center;
    }
    else if (e.Cell.ColumnIndex == 0)
    {
       e.Style.CellValue = e.Cell.RowIndex;
       e.Style.Font.FontWeight = Windows.UI.Text.FontWeights.Bold;
       e.Style.VerticalAlignment = VerticalAlignment.Center;
       e.Style.HorizontalAlignment = HorizontalAlignment.Center;
    }
    else
       e.Style.CellValue = String.Format("({0} , {1})", e.Cell.RowIndex, e.Cell.ColumnIndex);
}

{% endhighlight %}
{% endtabs %}

## Gridlines

Enabling grid lines creates a borders around all cells within the CellGrid. Grid lines can be shown or hided by using ShowGridLines property.
By default, the grid lines are visible in the SfCellGrid. If you want to hide the grid lines, then set the `ShowGridLines` property to false.

{% tabs %}
{% highlight c# %}

//To hide the grid lines

cellGrid.ShowGridLines = false;

{% endhighlight %}
{% endtabs %}

### Gridline Color

User can set any color to the grid lines in SfCellGrid using the `GridLineColor` property.

{% tabs %}
{% highlight c# %}

//Changing the color of the grid lines

cellGrid.GridLineColor = Brushes.Green;

{% endhighlight %}
{% endtabs %}

## Headers and Footers

Headers are the cells which represents the rows/columns at top while the footers are the cells which represents the rows/columns at bottom of the CellGrid.
SfCellGrid allows the user to set multiple header rows/columns and footer rows/columns. 

{% tabs %}
{% highlight c# %}

//Header rows

cellGrid.HeaderRows = 2;

//Header columns

cellGrid.HeaderColumns = 2;

//Footer rows

cellGrid.FooterRows = 2;

//Footer columns

cellGrid.FooterColumns = 2;

{% endhighlight %}
{% endtabs %}

## Refreshing the Grid

Refreshing the grid means forcing the grid cells to be repainted or resetting of GridStyleInfo objects in the view. SfCellGrid allows you to invalidate or refresh the view either by specifying the full range or particular range.
The range to be invalidated can be passed as `GridRangeInfo` object in the below methods.

{% tabs %}
{% highlight c# %}

//Invalidates the mentioned cell in the grid,
cellGrid.InvalidateCell(3, 3);

//Invalidates the range ,
var range = GridRangeInfo.Cells(5, 4, 6, 7);
cellGrid.InvalidateCell(range);

//Invalidates the range by setting the parameter as false to avoid the resetting of GridStyleInfo objects in the mentioned range,
var range = GridRangeInfo.Cells(5, 4, 6, 7);
cellGrid.InvalidateCell(range,false);

//Invalidates all the cells in the grid,
cellGrid.InvalidateCells();

//Invalidates all the cells in the grid by setting the parameter as false to avoid the resetting of GridStyleInfo objects,
cellGrid.InvalidateCells(false);

//Invalidates the measurement state(layout) of grid,
cellGrid.InvalidateVisual();

//Invalidates the measurement state(layout) of grid by setting the parameter as true to invalidate the layout of rows,
cellGrid.InvalidateVisual(true);

//Invalidates the measurement state(layout) of grid by setting the parameter as true to invalidate the layout of row in the mentioned range,
var range = GridRangeInfo.Cells(5, 4, 6, 7);
cellGrid.InvalidateVisual(true,range);

//Invalidates the cell borders in the range,
var range = GridRangeInfo.Cells(2, 4, 6, 4);
cellGrid.InvalidateCellBorders(range);

//Invalidates the selection layout,
cellGrid.InvalidateSelection();

{% endhighlight %}
{% endtabs %}

## Scrolling

### Auto Scrolling

SfCellGrid scrolls rows and columns automatically when the user drags the pressed mouse to an edge of the view. By default, auto scrolling is enabled in SfCellGrid.
But you can disable this auto scrolling by setting the `IsEnabled` property of `GridAutoScroller` to false.

{% tabs %}
{% highlight c# %}

//To disable the auto scrolling

cellGrid.AutoScroller.IsEnabled = false;

{% endhighlight %}
{% endtabs %}

### Programmatic Scrolling

SfCellGrid allows the user to scroll the grid into mentioned cell, by using `ScrollInView` method.

{% tabs %}
{% highlight c# %}

//Scrolls the grid to mentioned row and column index,
cellGrid.ScrollInView(new RowColumnIndex(5, 5));

{% endhighlight %}
{% endtabs %}

The other scrolling methods in SfCellGrid are

`ScrollToNextPage`      - Scrolls to next page in horizontal/vertical direction

`ScrollToPreviousPage`  - Scrolls to previous page in horizontal/vertical direction

{% tabs %}
{% highlight c# %}

//Scrolls to the next page in the row(moves to bottom),
cellGrid.ScrollRows.ScrollToNextPage();
cellGrid.InvalidateMeasure();
 
//Scrolls to the previous page in the row(moves to top),
cellGrid.ScrollRows.ScrollToPreviousPage();
cellGrid.InvalidateMeasure();
 
//Scrolls to the next page in the column(moves to right),
cellGrid.ScrollColumns.ScrollToNextPage();
cellGrid.InvalidateMeasure();
 
//Scrolls to the previous page in the colunn(moves to left),
cellGrid.ScrollColumns.ScrollToPreviousPage();
cellGrid.InvalidateMeasure();

{% endhighlight %}
{% endtabs %}
