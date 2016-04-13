---
layout: post
title: Rows and Columns 
description: Operations involved with rows and columns in SfSpreadsheet
platform: UWP
control: SfSpreadsheet
documentation: ug
---

# Rows and Columns
This section explains about the operations related with rows and columns in SfSpreadsheet

## Insert and Delete

### Inserting Rows and Columns

SfSpreadsheet provides support for dynamically inserting rows and columns into a worksheet. 

{% tabs %}
{% highlight c# %}

//For Inserting Rows

spreadsheet.ActiveSheet.InsertRow(2, 3);

spreadsheet.ActiveGrid.Model.InsertRows(2, 3);

//For Inserting Cols

spreadsheet.ActiveSheet.InsertColumn(3, 2);

spreadsheet.ActiveGrid.Model.InsertColumns(3, 2);

{% endhighlight %}
{% endtabs %}


### Deleting Rows and Columns

SfSpreadsheet provides support for deleting rows and columns from a worksheet,

{% tabs %}
{% highlight c# %}

//For Deleting Rows

spreadsheet.ActiveSheet.DeleteRow(5, 2);

spreadsheet.ActiveGrid.Model.RemoveRows(5, 2);

//For Deleting Cols

spreadsheet.ActiveSheet.DeleteColumn(3, 2);

spreadsheet.ActiveGrid.Model.RemoveColumns(3, 2);

{% endhighlight %}
{% endtabs %}


## Hide and Unhide


### Hiding Rows/Columns

SfSpreadsheet provides support to hide rows/columns and this can be done by `HideRow` and `HideColumn` method

{% tabs %}
{% highlight c# %}

//For Hiding Rows,

 spreadsheet.ActiveSheet.HideRow(5);

 spreadsheet.ActiveGrid.RowHeights.SetHidden(5, 5, true);

//For Hiding Cols,

 spreadsheet.ActiveSheet.HideColumn(4);

 spreadsheet.ActiveGrid.ColumnWidths.SetHidden(4, 4, true);

{% endhighlight %}
{% endtabs %}


### Unhiding Rows/Columns

Unhide the rows/columns in SfSpreadsheet can be done by `ShowRow` and `ShowColumn` methods.

{% tabs %}
{% highlight c# %}

//For Unhiding Rows,

 spreadsheet.ActiveSheet.ShowRow(5, true);

 spreadsheet.ActiveGrid.RowHeights.SetHidden(5, 5, false);

//For Unhiding Cols,

 spreadsheet.ActiveSheet.ShowColumn(4,true);

 spreadsheet.ActiveGrid.ColumnWidths.SetHidden(4, 4, false);

{% endhighlight %}
{% endtabs %}


## Row Height and Column Width

SfSpreadsheet provides support to adjust the row height and column width. And also can import the adjusted row height and column width from Excel. Spreadsheet provides support to fit the row and column based on its contents.

{% tabs %}
{% highlight c# %}

//For setting RowHeight for 4th Row

 spreadsheet.ActiveGrid.SetRowHeight(4, 4, 30);

 spreadsheet.ActiveGrid.InvalidateCell(GridRangeInfo.Row(4), true);

//For setting ColumnWidth for 5th Column

 spreadsheet.ActiveGrid.SetColumnWidth(5, 5, 22);

 spreadsheet.ActiveGrid.InvalidateCell(GridRangeInfo.Col(5), true);

{% endhighlight %}
{% endtabs %}


N> In case if you Insert/Delete and Hide/Unhide the rows/columns inside the Grouping, `RefreshOutlines` method must be invoked to refresh/update the Outlines of the Group.	

## Freeze Panes

SfSpreadsheet provides support for Freeze panes to keep an area of a worksheet visible while you scroll to another area of the worksheet

{% tabs %}
{% highlight c# %}

//Freezepanes

//To Freeze 4 rows and 4 columns

 spreadsheet.Workbook.ActiveSheet.Range[4, 4].FreezePanes();

 spreadsheet.ActiveGrid.FrozenRows = 5;

 spreadsheet.ActiveGrid.FrozenColumns = 5;

{% endhighlight %}
{% endtabs %}



