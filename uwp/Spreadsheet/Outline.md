---
layout: post
title: Outline in UWP Spreadsheet control | Syncfusion®
description: Learn here all about Outline support in Syncfusion® UWP Spreadsheet (SfSpreadsheet) control and more.
platform: UWP
control: SfSpreadsheet
documentation: ug
---

# Outline in UWP Spreadsheet (SfSpreadsheet)

SfSpreadsheet provides support for outlines like in excel which makes your data easier to view. You can group or ungroup the data’s either by rows or columns.

## Group rows and columns

SfSpreadsheet provides support to group the specified range in a worksheet.

To `Group` the rows/columns

{% tabs %}
{% highlight c# %}

//Group rows,
var gridRange = GridRangeInfo.Rows(4,8);
spreadsheet.Group(spreadsheet.ActiveSheet, gridRange, ExcelGroupBy.ByRows);

//Group columns,
var gridRange = GridRangeInfo.Cols(4,8);
spreadsheet.Group(spreadsheet.ActiveSheet, gridRange, ExcelGroupBy.ByColumns);

{% endhighlight %}
{% endtabs %}

## Ungroup rows and columns

SfSpreadsheet provides support to ungroup the specified range in a worksheet.

To `Ungroup` the rows/columns

{% tabs %}
{% highlight c# %}
//Ungroup rows,
var gridRange = GridRangeInfo.Rows(4,8);
spreadsheet.UnGroup(spreadsheet.ActiveSheet, gridRange, ExcelGroupBy.ByRows);

//Ungroup columns,
var gridRange = GridRangeInfo.Cols(4,8);
spreadsheet.UnGroup(spreadsheet.ActiveSheet, gridRange, ExcelGroupBy.ByColumns);

{% endhighlight %}
{% endtabs %}

## Collapse or Expand Group

Groups can be Expanded by `ExpandGroup` method  and Collapsed  by `CollapseGroup` method of XlsIO.

{% tabs %}
{% highlight c# %}

//Expand Rows,
spreadsheet.ActiveSheet.Range["A4:A8"].ExpandGroup(ExcelGroupBy.ByRows);
spreadsheet.ActiveGrid.RowHeights.SetHidden(4, 8, false);
spreadsheet.RefreshOutlines(true,false);

//Expand Columns,
spreadsheet.ActiveSheet.Range["A3:F3"].ExpandGroup(ExcelGroupBy.ByColumns);
spreadsheet.ActiveGrid.ColumnWidths.SetHidden(1, 6, false);
spreadsheet.RefreshOutlines(false,true);

//Collapse Rows,
spreadsheet.ActiveSheet.Range["A4:A8"].CollapseGroup(ExcelGroupBy.ByRows);
spreadsheet.ActiveGrid.RowHeights.SetHidden(4, 8, true);
spreadsheet.RefreshOutlines(true,false);

//Collapse Columns,
spreadsheet.ActiveSheet.Range["A3:F3"].CollapseGroup(ExcelGroupBy.ByColumns);
spreadsheet.ActiveGrid.ColumnWidths.SetHidden(1, 6, true);
spreadsheet.RefreshOutlines(false,true);

{% endhighlight %}
{% endtabs %}

N> `RefreshOutlines` method is invoked to refresh/update the Outlines of the Group in SfSpreadsheet.

## Change Outline Settings

In SfSpreadsheet, users can change the outline settings by changing the display of summary rows to either below or above the details and summary columns to  either left or right of the details in Outlines Group.

{% tabs %}
{% highlight c# %}

spreadsheet.ActiveSheet.PageSetup.IsSummaryRowBelow = false;
spreadsheet.ActiveSheet.PageSetup.IsSummaryColumnRight = false;
spreadsheet.RefreshOutlines(true, true);
            
{% endhighlight %}
{% endtabs %}

## Clear Outlines

SfSpreadsheet provides support to clear all the Outlines of the Grouped range.

{% tabs %}
{% highlight c# %}

var sheet = spreadsheet.Workbook.Worksheets[0] as WorksheetImpl;

foreach (OutlineWrapper outline in sheet.OutlineWrappers)
{
  outline.OutlineRange.Ungroup(outline.GroupBy);
}
spreadsheet.RefreshOutlines(true, true);

{% endhighlight %}
{% endtabs %}

