---
layout: post
title:  Find And Replace operation in SfSpreadsheet
description: Find and Replace operation in SfSpreadsheet
platform: UWP
control: SfSpreadsheet
documentation: ug
---

# Find and Replace

This section explains about Find and Replace operations in SfSpreadsheet. 

## Find 

Searches for specific data such as particular number or text according to specified options and returns an IRange representing the cell or null if no cell is found. The various options in Find operation are

* `FindAll`
* `FindNext`
* `FindCondtionalFormatting`
* `FindConstants`
* `FindFormulas`
* `FindDataValidation`

The common parameters to be passed in Find functions are,

* The option to specify whether the search can be done within the Workbook(`IWorkbook`) or Worksheet(`IWorksheet`).
* The text to be searched.
* The option to specify the direction whether the search can be done either by row wise or column wise using `SearchBy` enum.
* The type to specify whether the search can be done either in formulas or values using `ExcelFindType` enum.
* For a case sensitive search, pass the parameter as true otherwise you can pass the parameter as false.
* For matching the entire cell content with the search text, pass the parameter as true otherwise you can pass the parameter as false.

### Find All

Searches the every occurrence of specific data based on the criteria that you are searching for and returns an `IRange` list representing the cells in `SfSpreadsheet`

{% tabs %}
{% highlight c# %}

//Search the entire workbook
var list = spreadsheet.SearchManager.FindAll(spreadsheet.Workbook, "sample", SearchBy.ByRows, ExcelFindType.Text, false, true);

// To select the matched cell content ranges,

foreach (var cell in list)
{  
  spreadsheet.ActiveGrid.SelectionController.AddSelection(GridRangeInfo.Cell(cell.Row, cell.Column));          
}

//Search the particular worksheet
var list = spreadsheet.SearchManager.FindAll(spreadsheet.Workbook.Worksheets[0], "sample", SearchBy.ByRows, ExcelFindType.Text, false, true);

// To select the matched cell content ranges,

foreach (var cell in list)
{
  spreadsheet.ActiveGrid.SelectionController.AddSelection(GridRangeInfo.Cell(cell.Row, cell.Column));          
}

{% endhighlight %}
{% endtabs %}

### Find Next

Searches the next cell that matches those criterias and returns an immediate matched `IRange` that represents that cell. 

{% tabs %}
{% highlight c# %}

//Search the text in entire workbook in Column wise,

var cell = spreadsheet.SearchManager.FindNext(spreadsheet.Workbook, "sample", SearchBy.ByColumns, ExcelFindType.Text, false, true);

// To select the matched cell content range,

spreadsheet.ActiveGrid.SelectionController.AddSelection(GridRangeInfo.Cell(cell.Row, cell.Column));          

//Search the formula in particular worksheet in row wise,

var cell = spreadsheet.SearchManager.FindNext(spreadsheet.Workbook.Worksheets[0], "sum", SearchBy.ByRows, ExcelFindType.Text, false, false);

// To select the matched cell content range,

spreadsheet.ActiveGrid.SelectionController.AddSelection(GridRangeInfo.Cell(cell.Row, cell.Column));          

{% endhighlight %}
{% endtabs %}

### Find CondtionalFormatting

Searches and returns the `IRange` list which have conditional formatting within the specified worksheet.

{% tabs %}
{% highlight c# %}

//Searches the conditional formatting within the worksheet,

var list = spreadsheet.SearchManager.FindConditionalFormatting(spreadsheet.Workbook.Worksheets[0]);

// To select the matched cell content ranges,

foreach (var cell in list)
{
  spreadsheet.ActiveGrid.SelectionController.AddSelection(GridRangeInfo.Cell(cell.Row, cell.Column));          
}

{% endhighlight %}
{% endtabs %}

### Find Constants

Searches and returns the `IRange` list which have constants within the specified worksheet.

{% tabs %}
{% highlight c# %}

//Searches the constants within the worksheet,

var list = spreadsheet.SearchManager.FindConstants(spreadsheet.Workbook.Worksheets[0]);

// To select the matched cell content ranges,

foreach (var cell in list)
{
   spreadsheet.ActiveGrid.SelectionController.AddSelection(GridRangeInfo.Cell(cell.Row, cell.Column));         
}

{% endhighlight %}
{% endtabs %}

### Find Formulas

Searches and returns the `IRange` list which have formulas within the specified worksheet.

{% tabs %}
{% highlight c# %}

//Searches the formulas within the worksheet,

var list = spreadsheet.SearchManager.FindFormulas(spreadsheet.Workbook.Worksheets[0]);

// To select the matched cell content ranges,

foreach (var cell in list)
{
   spreadsheet.ActiveGrid.SelectionController.AddSelection(GridRangeInfo.Cell(cell.Row, cell.Column));          
}

{% endhighlight %}
{% endtabs %}

### Find DataValidation

Searches and returns the `IRange` list which have data validation within the specified worksheet.

{% tabs %}
{% highlight c# %}

//Searches the data validation within the worksheet,

var list = spreadsheet.SearchManager.FindDataValidation(spreadsheet.Workbook.Worksheets[0]);

// To select the matched cell content ranges,

foreach (var cell in list)
{
   spreadsheet.ActiveGrid.SelectionController.AddSelection(GridRangeInfo.Cell(cell.Row, cell.Column));        
}

{% endhighlight %}
{% endtabs %}

## Replace

Searches for the text or numbers that you want to change and replace it with specified text or numbers in SfSpreadsheet.

{% tabs %}
{% highlight c# %}

//Searches the given text and replaces it with specified text

var cell = spreadsheet.SearchManager.FindNext(spreadsheet.Workbook, "sample", SearchBy.ByColumns, ExcelFindType.Text, false, true);
spreadsheet.ActiveGrid.SetCellValue(cell, "sync");

{% endhighlight %}
{% endtabs %}

### Replace All

Searches and replaces all the texts either in the workbook or worksheet based on the given option.

The parameters to be passed in `ReplaceAll` function is,

* The option to specify whether the search can be done within the Workbook(`IWorkbook`) or Worksheet(`IWorksheet`) in SfSpreadsheet.
* The text to be searched.
* The text to be replaced.
* For a case sensitive search, pass the parameter as true otherwise you can pass the parameter as false.
* For matching the entire cell content with the search text, pass the parameter as true otherwise you can pass the parameter as false.

{% tabs %}
{% highlight c# %}

//Replaces the text in the entire workbook
spreadsheet.SearchManager.ReplaceAll(spreadsheet.Workbook, "sample","Sync", false, false);

//Replaces the text in the particular worksheet
spreadsheet.SearchManager.ReplaceAll(spreadsheet.Workbook.Worksheets[0], "sample", "sync", false, true);

{% endhighlight %}
{% endtabs %}



