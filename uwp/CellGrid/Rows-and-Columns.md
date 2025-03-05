---
layout: post
title: Rows and Columns in UWP CellGrid control | Syncfusion®
description: Learn here all about Rows and Columns support in Syncfusion® UWP CellGrid (SfCellGrid) control and more.
platform: uwp
control: SfCellGrid
documentation: ug
---

# Rows and Columns in UWP CellGrid (SfCellGrid)

This section explains the operations related with rows and columns in the SfCellGrid.

## Insert rows and columns

The SfCellGrid provides support for dynamically inserting rows and columns at a given position. 

{% tabs %}
{% highlight c# %}

//For inserting 5 rows at index 2,

cellGrid.Model.InsertRows(2, 5);

//For inserting 5 columns at index 3,

cellGrid.Model.InsertColumns(3, 5);

{% endhighlight %}
{% endtabs %}

### Events related with insertion

After inserting rows and columns in the SfCellGrid, the `RowsInserted` and `ColumnsInserted` events will be invoked to get the number of inserted rows or columns and the insertion index.

{% tabs %}
{% highlight c# %}

//Invoking the events,
cellGrid.Model.RowsInserted += Model_RowsInserted;
cellGrid.Model.ColumnsInserted += Model_ColumnsInserted;

private void Model_ColumnsInserted(object sender, GridRangeInsertedEventArgs e)
{
    //Number of columns inserted,
    var count = e.Count;

    //inserted position,
    var index = e.InsertAt;
}

private void Model_RowsInserted(object sender, GridRangeInsertedEventArgs e)
{
    //Number of rows inserted,
    var count = e.Count;

    //inserted position,
    var index = e.InsertAt;
}

{% endhighlight %}
{% endtabs %}

## Delete rows and columns

The SfCellGrid provides support for deleting rows and columns from the given position.

{% tabs %}
{% highlight c# %}

//For deleting 2 rows at index 5,

cellGrid.Model.RemoveRows(5, 2);

//For deleting 5 columns at index 3,

cellGrid.Model.RemoveColumns(3, 5);

{% endhighlight %}
{% endtabs %}

### Events related with deletion

After deleting rows and columns, the `RowsRemoved` and `ColumnsRemoved` events will be invoked to get the number of rows or columns deleted and the deletion index.

{% tabs %}
{% highlight c# %}

//Invoking the events,
cellGrid.Model.RowsRemoved += Model_RowsRemoved;
cellGrid.Model.ColumnsRemoved += Model_ColumnsRemoved;

private void Model_ColumnsRemoved(object sender, GridRangeRemovedEventArgs e)
{
    //Number of columns deleted,
    var count = e.Count;

    //Deleted position,
    var index = e.RemoveAt;
}

private void Model_RowsRemoved(object sender, GridRangeRemovedEventArgs e)
{
    //Number of rows deleted,
    var count = e.Count;

    //Deleted position,
    var index = e.RemoveAt;
}
            
{% endhighlight %}
{% endtabs %}

## Hide rows and columns

The SfCellGrid provides support to hide rows or columns by passing the last argument as `true` in the `SetHidden` method of `RowHeights` and `ColumnWidths` properties.

{% tabs %}
{% highlight c# %}

//For hiding the rows from 5 to 7,

cellGrid.RowHeights.SetHidden(5, 7, true);

//For hiding the columns from 4 to 5,

cellGrid.ColumnWidths.SetHidden(4, 5, true);

{% endhighlight %}
{% endtabs %}

## Unhide rows and columns

Unhide the rows or columns in the SfCellGrid by passing the last argument as `false` in the `SetHidden` method of `RowHeights` and `ColumnWidths` properties.

{% tabs %}
{% highlight c# %}

//For unhiding rows from 5 to 6,
cellGrid.RowHeights.SetHidden(5, 6, false);

//For unhiding the columns from 3 to 7,
cellGrid.ColumnWidths.SetHidden(3, 7, false);

{% endhighlight %}
{% endtabs %}

## Events related with hiding or unhiding

After hiding the rows or columns, the `LineHiddenChanged` event for the row heights or column widths will be invoked.

{% tabs %}
{% highlight c# %}

cellGrid.RowHeights.LineHiddenChanged += RowHeights_LineHiddenChanged;
cellGrid.ColumnWidths.LineHiddenChanged += ColumnWidths_LineHiddenChanged;

private void RowHeights_LineHiddenChanged(object sender, HiddenRangeChangedEventArgs e)
{
    var startRow = e.From;
    var endRow = e.To;           
}

private void ColumnWidths_LineHiddenChanged(object sender, HiddenRangeChangedEventArgs e)
{           
    var startColumn = e.From;
    var endColumn = e.To;         
}

{% endhighlight %}
{% endtabs %}


## Row height and column width

The SfCellGrid provides support to adjust the row height and column width by using the `SetRowHeight` and `SetColumnWidth` methods.

{% tabs %}
{% highlight c# %}

//For setting RowHeight from 4 to 6th row

cellGrid.SetRowHeight(4, 6, 30);

//For setting ColumnWidth from 5 to 8th column

cellGrid.SetColumnWidth(5, 8, 60);

//To set default RowHeight/ColumnWidth for entire grid,

cellGrid.RowHeights.DefaultLineSize = 50;
cellGrid.ColumnWidths.DefaultLineSize = 80;

{% endhighlight %}
{% endtabs %}

### Events related with RowHeight or ColumnWidth

After changing the row height or column width in the SfCellGrid, the `LineSizeChanged` event for row heights or column widths will be invoked to get old and resized heights or widths of the rows or columns.

{% tabs %}
{% highlight c# %}

//Invoking the RowHeights/ColumnWidths changed events,
 
cellGrid.RowHeights.LineSizeChanged += RowHeights_LineSizeChanged;
cellGrid.ColumnWidths.LineSizeChanged += ColumnWidths_LineSizeChanged;

private void RowHeights_LineSizeChanged(object sender, RangeChangedEventArgs e)
{         
    var oldSize = e.OldSize;
    var newSize = e.NewSize;      
}

private void ColumnWidths_LineSizeChanged(object sender, RangeChangedEventArgs e)
{
    var oldSize = e.OldSize;
    var newSize = e.NewSize;
}

//Invoking the default RowHeight/ColumnWidth changed events,

cellGrid.RowHeights.DefaultLineSizeChanged += RowHeights_DefaultLineSizeChanged;
cellGrid.ColumnWidths.DefaultLineSizeChanged += ColumnWidths_DefaultLineSizeChanged;

private void RowHeights_DefaultLineSizeChanged(object sender, DefaultLineSizeChangedEventArgs e)
{
    var oldSize = e.OldSize;
    var newSize = e.NewSize;       
}

private void ColumnWidths_DefaultLineSizeChanged(object sender, DefaultLineSizeChangedEventArgs e)
{
    var oldSize = e.OldSize;
    var newSize = e.NewSize;
}

{% endhighlight %}
{% endtabs %}

## Freeze rows and columns

The SfCellGrid provides support to keep an area of a visible grid when scrolling to another area by fixing any number of rows and columns is called freezing.

{% tabs %}
{% highlight c# %}

//To Freeze 4 rows and 4 columns

cellGrid.FrozenRows = 4;

cellGrid.FrozenColumns = 4;

{% endhighlight %}
{% endtabs %}

## Unfreeze rows and columns

The SfCellGrid provides support to unfreeze the rows and columns by setting the `FrozenRows` and `FrozenColumns` counts to 1.

{% tabs %}
{% highlight c# %}

//To Unfreeze 4 rows and 4 columns

cellGrid.FrozenRows = 1;
cellGrid.FrozenColumns = 1;

{% endhighlight %}
{% endtabs %}

## Resize rows and columns

By default, row resizing and column resizing will be enabled in the SfCellGrid. To disable the resizing, set the `AllowRowResize` and `AllowColumnResize` properties to false.

{% tabs %}
{% highlight c# %}

//To disable row resizing
cellGrid.AllowRowResize = false;

//To disable column resizing
cellGrid.AllowColumnResize = false;

{% endhighlight %}
{% endtabs %}

### Hidden rows or columns resizing

By default, resizing will be enabled for hidden rows and columns. To disable the resizing, set the  `AllowHiddenRowResize` and `AllowHiddenColumnResize` properties to false.

{% tabs %}
{% highlight c# %}

//To disable row resizing
cellGrid.AllowHiddenRowResize = false;

//To disable column resizing
cellGrid.AllowHiddenColumnResize = false;

{% endhighlight %}
{% endtabs %}

### Resizing controller

Resizing controller of rows and columns can be customized and set to the `RowResizingController` and `ColumnResizingController` properties of the SfCellGrid.

Properties associated with `RowResizingController` and `ColumnResizingController` classes are:

* `HitTestPrecision`: Gets or sets the visible line when the mouse moves over the row or column.
* `TouchHitTestPrecision`: Gets or sets the visible line when the touch operation is performed over row or column.
* `ResizeColumnIndex`: Gets or sets the column index in the multiple header columns in which the row resizing operation will be performed.
* `ResizeRowIndex`: Gets or sets the row index in the multiple header rows in which the column resizing operation will be performed.

### Events related with resizing

When resizing the rows or columns, the corresponding `ResizingRows` and `ResizingColumns` events will be invoked to cancel the resizing operation or get the corresponding resizing row or column index and height or width.

{% tabs %}
{% highlight c# %}

cellGrid.ResizingColumns += CellGrid_ResizingColumns;
cellGrid.ResizingRows += CellGrid_ResizingRows;

private void CellGrid_ResizingRows(object sender, ResizingRowsEventArgs e)
{
    var rowindex = e.RowIndex;
    var height = e.Height;
    e.Cancel = true;

}

private void CellGrid_ResizingColumns(object sender, ResizingColumnsEventArgs e)
{
    var colIndex = e.ColumnIndex;
    var height = e.Width;
    e.Cancel = true;
}
            
{% endhighlight %}
{% endtabs %}           
            
### ResizeToFit

The SfCellGrid provides support to enable the resizing of rows and columns based on the cell content. The parameters passed in the method is of type `GridRangeInfo` that mentions the ranges of rows and columns to allow resizing and `GridResizeToFitOptions` enum that provides the user with the options to control the resizing behavior. 

The options in the `GridResizeToFitOptions` enum are:

* None: Resizes the cells to fit contents and shrinks size. It does not include covered cells and headers.
* NoShrinkSize: Does not shrink the size of cells.
* IncludeHeaders: Includes the row and column headers for resizing.

#### ResizeRowsToFit

Resizes the row height for the given range of row or rows based on the content size.

{% tabs %}
{% highlight c# %}

//Resizing of Rows from 5 to 7,
cellGrid.Model.ResizeRowsToFit(GridRangeInfo.Rows(5, 7), GridResizeToFitOptions.None);

{% endhighlight %}
{% endtabs %}

#### ResizeColumnsToFit

Resizes the column width for the given range of column or columns based on the content size.

{% tabs %}
{% highlight c# %}

//Resizing of Columns from 4 to 10,
cellGrid.Model.ResizeColumnsToFit(GridRangeInfo.Cols(4, 10), GridResizeToFitOptions.NoShrinkSize);

{% endhighlight %}
{% endtabs %}
