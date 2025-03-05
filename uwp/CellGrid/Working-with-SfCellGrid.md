---
layout: post
title: Working with CellGrid in UWP CellGrid control | Syncfusion®
description: Learn here all about Working with CellGrid support in Syncfusion® UWP CellGrid (SfCellGrid) control and more.
platform: uwp
control: SfCellGrid
documentation: ug
---

# Working with CellGrid in UWP CellGrid (SfCellGrid)
 This section explains about the virtualization behavior, programmatic scrolling and refreshing the grid.

## Virtualization

SfCellGrid provides support for virtualization in which data will be dynamically loaded into the grid through on demand or when the user needs to view the data.
SfCellGrid does not store the cell data in `GridStyleInfo` objects or any other internal grid storage. All information is provided while populating the data through the `QueryCellInfo` event, 
thus increasing the performance.

The `QueryCellInfo` event will be triggered for each cell when it comes into view. For more information, refer [QueryCellInfo](https://help.syncfusion.com/uwp/cellgrid/working-with-sfcellgrid#querycellinfo-event) topic.

## QueryCellInfo Event

The `QueryCellInfo` event of SfCellGrid is to populate the data at runtime.This event is used to provide `GridStyleInfo` object for a given cell. The `CellValue` property of the `GridStyleInfo` object holds the data. 
All the changes made in this event is done in on-demand basis and not stored in any internal storage.

This event allows you to customize cell contents at run-time on demand, just before the cell is drawn or programmatically accessed.
The event handler receives an argument of type `GridQueryCellInfoEventArgs` containing data related to this event. 

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
       e.Style.Background = new SolidColorBrush(Colors.Green);
	   e.Style.VerticalAlignment = VerticalAlignment.Center;
	   e.Style.HorizontalAlignment = HorizontalAlignment.Center;
    }
    else if (e.Cell.ColumnIndex == 0)
    {
       e.Style.CellValue = e.Cell.RowIndex;
       e.Style.Background = new SolidColorBrush(Colors.Pink);
       e.Style.Font.FontWeight = Windows.UI.Text.FontWeights.Bold;
       e.Style.VerticalAlignment = VerticalAlignment.Center;
       e.Style.HorizontalAlignment = HorizontalAlignment.Center;
    }
    else
       e.Style.CellValue = String.Format("({0} , {1})", e.Cell.RowIndex, e.Cell.ColumnIndex);
}

{% endhighlight %}
{% endtabs %}

N>`QueryCellInfo` event is used to provide the cell values on demand while the changes made in the grid will be saved back by the `CommitCellInfo` event.For more information,
please refer [here](https://help.syncfusion.com/uwp/cellgrid/working-with-sfcellgrid#commitcellinfo-event)

## CommitCellInfo Event

`CommitCellInfo` event save the changes made in the UI, to the external data source.The event handler receives an argument of type `GridCommitCellInfoEventArgs` containing data related to this event.
This event commits the changes in value and `GridStyleInfo` object for the cell in SfCellGrid.

{% tabs %}
{% highlight c# %}

Dictionary<RowColumnIndex, object> committedValues = new Dictionary<RowColumnIndex, object>();

// Loading Row and Column Count,

cellGrid.RowCount = 100; 

cellGrid.ColumnCount = 100;

//Invoking the event,

cellGrid.Model.CommitCellInfo += Model_CommitCellInfo;

//To commit the values at run time,

private void Model_CommitCellInfo(object sender, Syncfusion.UI.Xaml.CellGrid.Styles.GridQueryCellInfoEventArgs e)
{
    // save the updated cell value into dictionary,
    
    if (e.Style.HasCellValue)
    {
      committedValues[e.Cell] = e.Style.CellValue;
      e.Handled = true;
    }
}

{% endhighlight %}
{% endtabs %}

## Gridlines

Enabling grid lines creates a borders around all cells within the CellGrid. Grid lines can be shown or hidden by using `ShowGridLines` property.
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

Refreshing the grid means forcing the grid cells to be repainted or resetting of `GridStyleInfo` objects in the view. SfCellGrid allows you to invalidate or refresh the view either by specifying the full range or particular range.
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
cellGrid.InvalidateVisual();
 
//Scrolls to the previous page in the row(moves to top),
cellGrid.ScrollRows.ScrollToPreviousPage();
cellGrid.InvalidateVisual();
 
//Scrolls to the next page in the column(moves to right),
cellGrid.ScrollColumns.ScrollToNextPage();
cellGrid.InvalidateVisual();
 
//Scrolls to the previous page in the column(moves to left),
cellGrid.ScrollColumns.ScrollToPreviousPage();
cellGrid.InvalidateVisual();

{% endhighlight %}
{% endtabs %}

## How To

### How to get the Row and Column Index of the cell from Mouse Point?

In SfCellGrid, you can get the Row and Column Index of a cell under the Mouse Point, by using PointToCellRowColumnIndex and PointToCellRowColumnIndexOutsideCells.

#### PointToCellRowColumnIndex:

This method allows you to get the Row and Column Index of a cell under the mouse point in SfCellGrid, regardless of its position.

Syntax: PointToCellRowColumnIndex (Point p);

{% tabs %}
{% highlight c# %}

Point position =  Mouse.GetPosition(grid);
RowColumnIndex cell = grid.PointToCellRowColumnIndex(position);

{% endhighlight %}
{% endtabs %}

#### PointToCellRowColumnIndexOutsideCells:

This method allows you to get the Row and Column Index of the cell under the mouse point in SfCellGrid. It also allows you to identify whether you have clicked inside the cell or points outside the cell, that is, points over the gridlines.

Syntax: PointToCellRowColumnIndexOutsideCells(Point p, bool allowOutsideLines)

{% tabs %}
{% highlight c# %}

Point position =  Mouse.GetPosition(grid);
RowColumnIndex cell = cellGrid.PointToCellRowColumnIndexOutsideCells(position, false);

{% endhighlight %}
{% endtabs %}

T>You can easily identify whether you have clicked at any point inside the cell or outside the cell by setting allowOutsideLines as “False”. It returns negative values for the points that are outside the cell.

### How to remove the gridlines in SfCellGrid?

To remove the gridlines in SfCellGrid, then set the `ShowGridLines` property to false.

{% tabs %}
{% highlight c# %}

//To hide the grid lines

cellGrid.ShowGridLines = false;

{% endhighlight %}
{% endtabs %}

### How to reset the SfCellGrid?

To reset or refresh the cells, you need to invoke `InvalidateCells` method of SfCellGrid.

{% tabs %}
{% highlight c# %}

//Invalidates all the cells in the grid,
cellGrid.InvalidateCells();

{% endhighlight %}
{% endtabs %}
