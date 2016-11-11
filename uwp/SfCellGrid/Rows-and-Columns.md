---
layout: post
title: Rows and Columns Operations in SfCellGrid
description: Operations involved with rows and columns in SfCellGrid
platform: uwp
control: SfCellGrid
documentation: ug
---

# Rows and Columns

This section explains about the operations related with rows and columns in SfCellGrid.

## Insert Rows and Columns

SfCellGrid provides support for dynamically inserting rows and columns at a given position. 

{% tabs %}
{% highlight c# %}

//For inserting 5 rows at index 2,

cellGrid.Model.InsertRows(2, 5);

//For inserting 5 columns at index 3,

cellGrid.Model.InsertColumns(3, 5);

{% endhighlight %}
{% endtabs %}

### Events related with Insertion

After inserting the rows and columns in SfCellGrid, `RowsInserted` and `ColumnsInserted` events are invoked which is used to get the number of 
rows/columns inserted and the insertion index.

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

## Delete Rows and Columns

SfCellGrid provides support for deleting rows and columns from the given position.

{% tabs %}
{% highlight c# %}

//For deleting 2 rows at index 5,

cellGrid.Model.RemoveRows(5, 2);

//For deleting 5 columns at index 3,

cellGrid.Model.RemoveColumns(3, 5);

{% endhighlight %}
{% endtabs %}

### Events related with Deletion

After deleting rows and columns, `RowsRemoved` and `ColumnsRemoved` events will be invoked which is used to get the number of 
rows/columns deleted and the deletion index.

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

## Hide Rows and Columns

SfCellGrid provides support to hide rows/columns. This can be done by passing the last argument as `true` in `SetHidden` method of `RowHeights` and `ColumnWidths` property in SfCellGrid.

{% tabs %}
{% highlight c# %}

//For hiding the rows from 5 to 7,

cellGrid.RowHeights.SetHidden(5, 7, true);

//For hiding the columns from 4 to 5,

cellGrid.ColumnWidths.SetHidden(4, 5, true);

{% endhighlight %}
{% endtabs %}

## Unhide Rows and Columns

Unhide the rows/columns in SfCellGrid by passing the last argument as `false` in `SetHidden` method of `RowHeights` and `ColumnWidths` property.

{% tabs %}
{% highlight c# %}

//For unhiding rows from 5 to 6,
cellGrid.RowHeights.SetHidden(5, 6, false);

//For unhiding the columns from 3 to 7,
cellGrid.ColumnWidths.SetHidden(3, 7, false);

{% endhighlight %}
{% endtabs %}

## Events related with Hiding/Unhiding

After hiding the rows/columns, the `LineHiddenChanged` event for RowHeights/ColumnWidths will be invoked.

{% tabs %}
{% highlight c# %}

cellGrid.RowHeights.LineHiddenChanged += RowHeights_LineHiddenChanged;
cellGrid.ColumnWidths.LineHiddenChanged += ColumnWidths_LineHiddenChanged;

private void RowHeights_LineHiddenChanged(object sender, HiddenRangeChangedEventArgs e)
{
    var startrow = e.From;
    var endrow = e.To;           
}

private void ColumnWidths_LineHiddenChanged(object sender, HiddenRangeChangedEventArgs e)
{           
    var startcolumn = e.From;
    var endcolumn = e.To;         
}

{% endhighlight %}
{% endtabs %}


## Row Height and Column Width

SfCellGrid provides support to adjust the row height and column width by using `SetRowHeight` and `SetColumnWidth` method.

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

### Events related with RowHeight/ColumnWidth

After changing the row height or column width in SfCellGrid, `LineSizeChanged` event for RowHeights/ColumnWidths will be invoked which can be used to get
old and resized height/width of the row/column.

{% tabs %}
{% highlight c# %}

//Invoking the RowHeights/ColumnWidths changed events,
 
cellGrid.RowHeights.LineSizeChanged += RowHeights_LineSizeChanged;
cellGrid.ColumnWidths.LineSizeChanged += ColumnWidths_LineSizeChanged;

private void RowHeights_LineSizeChanged(object sender, RangeChangedEventArgs e)
{         
    var oldsize = e.OldSize;
    var newsize = e.NewSize;      
}

private void ColumnWidths_LineSizeChanged(object sender, RangeChangedEventArgs e)
{
    var oldsize = e.OldSize;
    var newsize = e.NewSize;
}

//Invoking the default RowHeight/ColumnWidth changed events,

cellGrid.RowHeights.DefaultLineSizeChanged += RowHeights_DefaultLineSizeChanged;
cellGrid.ColumnWidths.DefaultLineSizeChanged += ColumnWidths_DefaultLineSizeChanged;

private void RowHeights_DefaultLineSizeChanged(object sender, DefaultLineSizeChangedEventArgs e)
{
    var oldsize = e.OldSize;
    var newsize = e.NewSize;       
}

private void ColumnWidths_DefaultLineSizeChanged(object sender, DefaultLineSizeChangedEventArgs e)
{
    var oldsize = e.OldSize;
    var newsize = e.NewSize;
}

{% endhighlight %}
{% endtabs %}

## Freeze Rows and Columns

SfCellGrid provides support to keep an area of a grid visible while you scroll to another area. Thus, to fix any number of rows/columns
to visible even when the grid is scrolled is called Freezing.

{% tabs %}
{% highlight c# %}

//To Freeze 4 rows and 4 columns

cellGrid.FrozenRows = 4;

cellGrid.FrozenColumns = 4;

{% endhighlight %}
{% endtabs %}

## Unfreeze Rows and Columns

SfCellGrid provides support to unfreeze the rows/columns by setting the `FrozenRows` and `FrozenColumns` count to 1.

{% tabs %}
{% highlight c# %}

//To Unfreeze 4 rows and 4 columns

cellGrid.FrozenRows = 1;
cellGrid.FrozenColumns = 1;

{% endhighlight %}
{% endtabs %}

## Resize Rows/Columns

By default, row resizing and column resizing will be enabled in SfCellGrid. To disable the resizing, set the `AllowRowResize` and  `AllowColumnResize` properties to  false.

{% tabs %}
{% highlight c# %}

//To disable row resizing
cellGrid.AllowRowResize = false;

//To disable column resizing
cellGrid.AllowColumnResize = false;

{% endhighlight %}
{% endtabs %}

### Hidden Rows/Columns Resizing

By default, resizing will be enabled for hidden rows and columns. To disable the resizing, set the  `AllowHiddenRowResize` and `AllowHiddenColumnResize` properties to false.

{% tabs %}
{% highlight c# %}

//To disable row resizing
cellGrid.AllowHiddenRowResize = false;

//To disable column resizing
cellGrid.AllowHiddenColumnResize = false;

{% endhighlight %}
{% endtabs %}

### Resizing Controller

Resizing Controller of rows and columns can be customized and set to `RowResizingController` and `ColumnResizingController` properties of SfCellGrid.

The properties associated with `RowResizingController` and `ColumnResizingController` class are

* `HitTestPrecision` - Used to get or set the visible line when the mouse moves over row/column.

* `TouchHitTestPrecision` - Used to get or set the visible line when the touch operation is performed over row/column.

* `ResizeColumnIndex` - Used to get or set the column index in multiple header columns in which the row resizing operation will be performed.

* `ResizeRowIndex`    - Used to get or set the row index in multiple header rows in which the column resizing operation will be performed

### Events related with Resizing

While Resizing rows/columns, the corresponding events `ResizingRows` and `ResizingColumns` will be invoked which is used to cancel the resizing operation or get the corresponding resizing row/column index and height/width.

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
    var colindex = e.ColumnIndex;
    var height = e.Width;
    e.Cancel = true;
}
            
{% endhighlight %}
{% endtabs %}           
            
### ResizeToFit

SfCellGrid provides the supports to enable the resizing of rows and columns based on the content of cells. The parameters passed in 
the method is of type `GridRangeInfo`, which mention the ranges of rows and columns to allow resizing and `GridResizeToFitOptions` enum which
provides the user with the options to control the resizing behavior. 

The options in `GridResizeToFitOptions` enum are

* None            -  resizes the cells to fit contents and shrinks size. It does not include covered cells and headers.

* NoShrinkSize    -  does not shrink the size of cells.

* IncludeHeaders  -  includes row and column headers for resizing.


#### ResizeRowsToFit

Resizes the row height for the given range of row/rows based on the content size.

{% tabs %}
{% highlight c# %}

//Resizing of Rows  from 5 to 7,
cellGrid.Model.ResizeRowsToFit(GridRangeInfo.Rows(5, 7), GridResizeToFitOptions.None);

{% endhighlight %}
{% endtabs %}

#### ResizeColumnsToFit

Resizes the column width for the given range of column/columns based on the content size.

{% tabs %}
{% highlight c# %}

//Resizing of Columns from 4 to 10,
cellGrid.Model.ResizeColumnsToFit(GridRangeInfo.Cols(4, 10), GridResizeToFitOptions.NoShrinkSize);

{% endhighlight %}
{% endtabs %}