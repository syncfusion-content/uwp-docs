---
layout: post
title: Appearance in UWP CellGrid control | Syncfusion®
description: Learn here all about Appearance support in Syncfusion® UWP CellGrid (SfCellGrid) control and more.
platform: uwp
control: SfCellGrid
documentation: ug
---

# Appearance in UWP CellGrid (SfCellGrid)

This section explains about customizing the appearance of SfCellGrid. 

## Covered Cells

Covered Cells are combination of cells that span over neighboring cells. The combined cells will act as single cell visually and programmatically. 
There are different possible options to form a covered range. The range can be range of cells, rows or columns.

### Creating Covered Range

To create a covered cell, users need to add `CoveredCellInfo` item to the `CoveredCells` of SfCellGrid.

{% tabs %}
{% highlight c# %}

//Adding covered range for range of cells,

cellGrid.CoveredCells.Add(new CoveredCellInfo(3, 4, 8, 6));           

{% endhighlight  %}
{% endtabs %}

### Creating Covered Range using Event

`QueryCoveredRange` is an event used to define covered ranges at runtime in the required cells. This event will be triggered when a cell comes into the view.
It receives an argument of type `GridQueryCoveredRangeEventArgs` containing the following information about the event.

<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
<code>Cell</code></td><td>
Gets the value indicating the instance of specified cell. </td></tr>
<tr>
<td>
<code>Handled</code></td><td>
Gets or sets whether the event should be handled or not. </td></tr>
<tr>
<td>
<code>Range</code></td><td>
Gets or sets the covered range of cell. </td></tr>
</table>

{% tabs %}
{% highlight c# %}

cellGrid.Model.QueryCoveredRange += Model_QueryCoveredRange;

private void Model_QueryCoveredRange(object sender, GridQueryCoveredRangeEventArgs e)
{           
    var row = e.Cell.RowIndex;
    var column = e.Cell.ColumnIndex;
    
    if (row == 2 && column == 2)
    {
        e.Range = new CoveredCellInfo(row, column, row + 3, column + 2);
        e.Handled = true;
    }              
}         

{% endhighlight  %}
{% endtabs %}

### Clearing the Covered Range

Covered cells in SfCellGrid can be removed by using `Clear` method.

{% tabs %}
{% highlight c# %}

//To clear all the covered cells,
cellGrid.CoveredCells.Clear();
cellGrid.InvalidateCells();

//To clear the covered cell in the given range,
var range = GridRangeInfo.Cells(3, 4, 8, 6);
cellGrid.CoveredCells.Clear(range);
cellGrid.InvalidateCell(range);

{% endhighlight  %}
{% endtabs %}

### Finding the Covered Range

To find covered range of a cell, `Find` method is used. If the given row/column index exists in the covered range, then the method returns true. Otherwise it returns false.

{% tabs %}
{% highlight c# %}

GridRangeInfo range;
bool isCovered = cellGrid.CoveredCells.Find(3, 4, out range);

{% endhighlight  %}
{% endtabs %}

## Floating Cells 

Floating cells are the cells in which if the content exceeds the length of the cell, then content will be floated to the adjacent cell if empty.
By default, the floating cell behavior will be enabled in SfCellGrid. If you want to disable, then set `AllowFloatingCell` property to false.

{% tabs %}
{% highlight c# %}

//To disable the floating cell behavior,

cellGrid.AllowFloatingCell = false;

{% endhighlight  %}
{% endtabs %}

By default, in edit mode the content will be floated to the adjacent cell. But if you want to disable the floating in edit mode, then set `AllowFloatingCellInEdit` 
property to false.

{% tabs %}
{% highlight c# %}

//To disable the floating cell behavior in edit mode,

cellGrid.AllowFloatingCellInEdit = false;

{% endhighlight  %}
{% endtabs %}

## Conditional Formatting

Conditional formatting is a process of applying customized styles to any object based on specified conditions. SfCellGrid allows the user to format the cells based on a certain condition.

Conditional formatting can be applied to SfCellGrid by using `ConditionalFormats` property which is an observable collection, where the users can add required number of formats of type `GridConditionalFormat`.
Using the `GridConditionalFormat` class, users can specify the criteria for the cells such as `GridConditionalFormatType`, `GridConditionType` and the value. The `Style` property of GridConditionalFormat class is used to set the specific styles for the cells.
Once these specifications are defined, the defined styles are applied to only those cells which satisfy the condition.

N>To determine whether the conditional formats has been applied to cell or range, `HasConditionalFormats` property is used.

### CellValue Format Type

To set the conditional format based on cell value, define the `GridConditionalFormatType` as `CellValue` and set any one of the options in `GridConditionType` enum followed with value in the `GridConditionalFormat` constructor.
Then set other formatting options such as background, foreground, font styles, etc., to the specified cell range. 

{% tabs %}
{% highlight c# %}

//Condition is set as greater than 30 for cell (3,3),
var format = new GridConditionalFormat(GridConditionalFormatType.CellValue, GridConditionType.GreaterThan,30);
format.Style.Background = new SolidColorBrush(Colors.Green);
format.Style.Foreground = new SolidColorBrush(Colors.Red);
format.Style.Font.FontWeight = FontWeights.Bold;
cellGrid.Model[3, 3].ConditionalFormats = new GridConditionalFormats();
cellGrid.Model[3, 3].ConditionalFormats.Add(format);

//Condition is set as less or equal to 70 for cell (7,7),
var format1 = new GridConditionalFormat(GridConditionalFormatType.CellValue, GridConditionType.LessThanOrEqual, 70);
format1.Style.Background = new SolidColorBrush(Colors.OrangeRed);
cellGrid.Model[7, 7].ConditionalFormats = new GridConditionalFormats();
cellGrid.Model[7, 7].ConditionalFormats.Add(format1);

//Condition is set as between 200 and 450 for cell (5,9),
var format2 = new GridConditionalFormat(GridConditionalFormatType.CellValue, GridConditionType.Between, 200, 450);
format2.Style.Background = new SolidColorBrush(Colors.DarkCyan);
cellGrid.Model[5, 9].ConditionalFormats = new GridConditionalFormats();
cellGrid.Model[5, 9].ConditionalFormats.Add(format2);

{% endhighlight  %}
{% endtabs %}

### Specific Text Format Type

To set the conditional format based on some text, define the `GridConditionalFormatType` as `SpecificText` and set any one of the options in `GridConditionType` enum followed with value in the `GridConditionalFormat` constructor.
Then set other formatting options such as background, foreground, font styles, etc., to the specified cell range.

{% tabs %}
{% highlight c# %}

//Condition is set as text in the cell (5,5) start with "A",
var format = new GridConditionalFormat(GridConditionalFormatType.SpecificText, GridConditionType.BeginsWith, "A");
format.Style.Background = new SolidColorBrush(Colors.Tomato);
cellGrid.Model[5, 5].ConditionalFormats = new GridConditionalFormats();
cellGrid.Model[5, 5].ConditionalFormats.Add(format);

{% endhighlight  %}
{% endtabs %}

### DatesOccurring Format Type

To set the conditional format based on DateTime, define the `GridConditionalFormatType` as `DatesOccurring` in the `GridConditionalFormat` constructor and set the condition `TimePeriodType`. 
Then set other formatting options such as background, foreground, font styles, etc., to the specified cell range.

{% tabs %}
{% highlight c# %}

var format = new GridConditionalFormat(GridConditionalFormatType.DatesOccurring);
format.Condition.TimePeriodType = GridTimePeriodType.Today;
cellGrid.Model[5, 5].CellValue = DateTime.Today.Date;
format.Style.Foreground = new SolidColorBrush(Colors.Blue);;
cellGrid.Model[5, 5].ConditionalFormats = new GridConditionalFormats();
cellGrid.Model[5, 5].ConditionalFormats.Add(format);

{% endhighlight  %}
{% endtabs %}        

### Blank Format Type

To set the conditional format based on empty cells, define the `GridConditionalFormatType` as `Blank` in the `GridConditionalFormat` constructor and 
set other formatting options such as background, foreground, font styles, etc., to the specified cell range.

{% tabs %}
{% highlight c# %}

var format = new GridConditionalFormat(GridConditionalFormatType.Blank);
format.Style.Background = new SolidColorBrush(Colors.Olive);
cellGrid.Model[5, 5].ConditionalFormats = new GridConditionalFormats();
cellGrid.Model[5, 5].ConditionalFormats.Add(format);

{% endhighlight  %}
{% endtabs %}

### No Blank Format Type

To set the conditional format based on non-empty cells, define the `GridConditionalFormatType` as `NoBlank` in the `GridConditionalFormat` constructor and 
set other formatting options such as background, foreground, font styles, etc., to the specified cell range.

{% tabs %}
{% highlight c# %}

var format = new GridConditionalFormat(GridConditionalFormatType.NoBlank);
format.Style.Background = new SolidColorBrush(Colors.Olive);
cellGrid.Model[5, 5].ConditionalFormats = new GridConditionalFormats();
cellGrid.Model[5, 5].ConditionalFormats.Add(format);

{% endhighlight  %}
{% endtabs %}          
            
### Formula Format Type

To set the conditional format based on Formula, define the define the `GridConditionalFormatType` as `Formula` in the `GridConditionalFormat` constructor and 
set condition, other formatting options such as background, foreground, font styles, etc., to the specified cell range.

{% tabs %}
{% highlight c# %}

var format = new GridConditionalFormat(GridConditionalFormatType.Formula);
format.Condition.Value1 = "=(A1+A2)> 50";          
format.Style.Background = new SolidColorBrush(Colors.BlueViolet);
cellGrid.Model[5, 5].ConditionalFormats = new GridConditionalFormats();
cellGrid.Model[5, 5].ConditionalFormats.Add(format);
            
{% endhighlight  %}
{% endtabs %}

N> Users need to invalidate the cells using `InvalidateCell(rowIndex,colIndex)` method, if the conditional formatting is applied at runtime like button click event. For more info, please refer [here](http://help.syncfusion.com/uwp/sfcellgrid/working-with-sfcellgrid#refreshing-the-grid).

### ResetConditionalFormats

To set the conditional format information of cell, `ConditionalFormats` property is used and to reset the conditional format information, `ResetConditionalFormats` method is used.

{% tabs %}
{% highlight c# %}
   
//To set conditional format for cell (5,5)
var conditionalFormat = new GridConditionalFormat(GridConditionalFormatType.NoBlank);
conditionalFormat.Style.Background = new SolidColorBrush(Colors.Olive);
cellGrid.Model[5, 5].ConditionalFormats = new GridConditionalFormats();
cellGrid.Model[5, 5].ConditionalFormats.Add(conditionalFormat);

//To reset the conditional format for cell(5,5)
cellGrid.Model[5, 5].ResetConditionalFormats();

{% endhighlight  %}
{% endtabs %}
