---
layout: post
title: Editing in UWP Spreadsheet control | Syncfusion®
description: Learn here all about Editing support in Syncfusion® UWP Spreadsheet (SfSpreadsheet) control and more.
platform: UWP
control: SfSpreadsheet
documentation: ug
---

# Editing in UWP Spreadsheet (SfSpreadsheet)

This section explains about the Editing behavior, Data Validation and Hyperlinks in SfSpreadsheet.

## Editing

The SfSpreadsheet control provides support for editing, you can modify and commit the cell values in the workbook.

By default, Editing will be enabled in `SfSpreadsheet`,but if you want to disable the editing in SfSpreadsheet, then set the `AllowEditing` Property to be false.

{% tabs %}
{% highlight c# %}

void spreadsheet_WorkbookLoaded(object sender, WorkbookLoadedEventArgs args)
{
    spreadsheet.ActiveGrid.AllowEditing = false;
}

{% endhighlight %}
{% endtabs %}

### Editing a cell programmatically

#### Start Editing
    
User can edit a cell programmatically by using `BeginEdit` method.

{% tabs %}
{% highlight c# %}

    spreadsheet.ActiveGrid.CurrentCell.BeginEdit(true);

{% endhighlight %}
{% endtabs %}

#### End Editing

User can end the editing of a cell programmatically in any of the following way,

* `ValidateAndEndEdit` - Validates and ends the edit operation for the current cell. if the cancel is "true", then the current cell remains in edit mode else if the validation is true, commits the new value and moved to next cell or else if the validation is false, it reverts the old value and moved to next cell.

* `EndEdit`   - Commits and ends the edit operation for the current cell, if it is passed with parameter _"true"_, commits the new changes for the cell, else reverts the old value.

{% tabs %}
{% highlight c# %}

//Validates and end the edit operation,
spreadsheet.ActiveGrid.CurrentCell.ValidateAndEndEdit();

//Commits the value and end the edit operation,
spreadsheet.ActiveGrid.CurrentCell.EndEdit(true);

{% endhighlight %}
{% endtabs %}

### Locking or Unlocking a cell

Locking cells allows you to disable editing and formatting the cells when the sheet is protected. By default, every cells are locked in the worksheet.
But while in protect mode, if you want to edit or format a cell, you can unlock the cells.

{% tabs %}
{% highlight c# %}

var worksheet = spreadsheet.ActiveSheet;
var excelStyle = worksheet.Range["A2"].CellStyle;

//To unlock a cell,           
excelStyle.Locked = false;

//To lock a cell, 
excelStyle.Locked = true; 

{% endhighlight %}
{% endtabs %}

### Properties, Methods and Events

The order of events when editing and committing a cell value in SfSpreadsheet,

<table>
<tr>
<th>
Events</th><th>
Description</th></tr>
<tr>
<td>
<code>CurrentCellBeginEdit</code></td><td>
Occurs when the current cell enters into edit mode. This event allows to cancel entering the edit mode.</td></tr>
<tr>
<td>
<code>CurrentCellValueChanged</code></td><td>
Occurs when the current cell value is changed in edit mode.</td></tr>
<tr>
<td>
<code>CurrentCellValidating</code></td><td>
Occurs when the current cell value is going to be validated. It allows you to validate and cancel the end editing.</td></tr>
<tr>
<td>
<code>CurrentCellValidated</code></td><td>
Occurs after the current cell is validated.</td></tr>
<tr>
<td>
<code>CurrentCellEndEdit</code></td><td>
Occurs when the current cell leaves from edit mode.</td></tr>
</table>

Below table list the properties associated with Editing.

<table>
<tr>
<th>
Properties</th><th>
Description</th></tr>
<tr>
<td>
<code>AllowEditing</code></td><td>
Gets or sets the value indicating whether to allow the editing operation or not.</td></tr>
<tr>
<td>
<code>EditorSelectionBehavior</code></td><td>
Gets or sets a value indicating whether editor select all the value or move last position.</td></tr>
<tr>
<td>
<code>EditTrigger</code></td><td>
Gets or sets a value indicating any of the trigger options will cause cells to enter Edit Mode.</td></tr>
<tr>
<td>
<code>IsEditing</code></td><td>
Gets  whether the current cell is in edit mode or not.</td></tr>
</table>

Below table list the methods associated with Editing.

<table>
<tr>
<th>
Methods</th><th>
Description</th></tr>
<tr>
<td>
<code>BeginEdit</code></td><td>
Begins the editing operation of the current cell and returns true if the current cell enters into edit mode.</td></tr>
<tr>
<td>
<code>EndEdit</code></td><td>
Commits and ends the edit operation of the current cell.</td></tr>
<tr>
<td>
<code>ValidateAndEndEdit</code></td><td>
Validates and ends the edit operation of the current cell.</td></tr>
<tr>
<td>
<code>Validate</code></td><td>
Validates the current cell in the SpreadsheetGrid.</td></tr>
</table>

## Data Validation

Data Validation is a list of rules to limit the type of data or the values that can be entered in the cell.

### Applying Data Validation at runtime

SfSpreadsheet allows the user to apply the data validation rules at runtime for particular cell or range using `IDataValidation` interface.

{% tabs %}
{% highlight c# %}

//Number Validation
IDataValidation validation = spreadsheet.ActiveSheet.Range["A5"].DataValidation;

validation.AllowType = ExcelDataType.Integer;
validation.CompareOperator = ExcelDataValidationComparisonOperator.Between;
validation.FirstFormula = "4";
validation.SecondFormula = "15";
validation.ShowErrorBox = true;
validation.ErrorBoxText = "Accepts values only between 4 to 15";


//Date Validation
IDataValidation validation = spreadsheet.ActiveSheet.Range["B4"].DataValidation;

validation.AllowType = ExcelDataType.Date;
validation.CompareOperator = ExcelDataValidationComparisonOperator.Greater;
validation.FirstDateTime = new DateTime(2016,5,5);
validation.ShowErrorBox = true;
validation.ErrorBoxText = "Enter the date value which is greater than 05/05/2016";

//TextLength Validation
IDataValidation validation = spreadsheet.ActiveSheet.Range["A3:B3"].DataValidation;

validation.AllowType = ExcelDataType.TextLength;
validation.CompareOperator = ExcelDataValidationComparisonOperator.LessOrEqual;
validation.FirstFormula = "4";
validation.ShowErrorBox = true;
validation.ErrorBoxText = "Text length should be lesser than or equal 4 characters";

//List Validation
IDataValidation validation = spreadsheet.ActiveSheet.Range["D4"].DataValidation;

validation.ListOfValues = new string[] { "10", "20", "30" };

//Custom Validation
IDataValidation validation = spreadsheet.ActiveSheet.Range["D4"].DataValidation;

validation.AllowType = ExcelDataType.Formula;
validation.FirstFormula = "=A1+A2>0";
validation.ErrorBoxText = "Sum of the values in A1 and A2 should be greater than zero";

{% endhighlight %}
{% endtabs %}

For more reference, please go through the [XlsIO](http://help.syncfusion.com/file-formats/xlsio/working-with-data-validation) UG.

T> If you want to load ComboBox to a cell in SfSpreadsheet, you can apply List Validation to that cell.

## Hyperlink

The Hyperlink is a convenient way to access the web pages, files and browse the data within a worksheet or other worksheets in a workbook. SfSpreadsheet provides support to add, edit and remove the Hyperlinks in the workbook.

### Add a Hyperlink to a cell

SfSpreadsheet provides support to add hyperlink to a cell and it can be added in the hyperlinks collection using `IHyperlinks` interface. 

SfSpreadsheet allows you to add below types of the hyperlink.

* Web URL
* Cell or range in workbook
* E-mail
* External files

{% tabs %}
{% highlight c# %}

// Creating a Hyperlink for e-mail,
var range = spreadsheet.ActiveSheet.Range["A5"];

IHyperLink hyperlink1 = spreadsheet.ActiveSheet.HyperLinks.Add(range);
hyperlink1.Type = ExcelHyperLinkType.Url;
hyperlink1.Address = "mailto:Username@syncfusion.com";
hyperlink1.TextToDisplay="Send Mail";
spreadsheet.ActiveGrid.InvalidateCell(GridRangeInfo.Cell(5, 1));

// Creating a Hyperlink for Opening Files,
var range1 = spreadsheet.ActiveSheet.Range["D5"];

IHyperLink hyperlink2 = spreadsheet.ActiveSheet.HyperLinks.Add(range1);
hyperlink2.Type = ExcelHyperLinkType.File;
hyperlink2.Address = @"C:\Samples\Local";
hyperlink2.TextToDisplay = "File Location";
spreadsheet.ActiveGrid.InvalidateCell(GridRangeInfo.Cell(5, 4));

//Creating a Hyperlink to refer another cell in the workbook,
var range2 = spreadsheet.ActiveSheet.Range["C13"];

IHyperLink hyperlink3 = spreadsheet.ActiveSheet.HyperLinks.Add(range);
hyperlink3.Type = ExcelHyperLinkType.Workbook;
hyperlink3.Address = "Sheet2!C23";
hyperlink3.TextToDisplay = "Sample";
spreadsheet.ActiveGrid.InvalidateCell(GridRangeInfo.Cell(13, 3));

{% endhighlight %}
{% endtabs %}

### Edit or Remove a Hyperlink

SfSpreadsheet provides support to edit or remove the hyperlinks from the range by accessing Hyperlinks collection.

{% tabs %}
{% highlight c# %}

//To Edit a hyperlink in a cell,
var hyperlink = spreadsheet.ActiveSheet.Range["A5"].Hyperlinks[0];
hyperlink.TextToDisplay = "Sample";
hyperlink.Address = "http://help.syncfusion.com";
spreadsheet.ActiveGrid.InvalidateCell(GridRangeInfo.Cell(5,1));

//To remove a hyperlink in a cell,
var hyperlink = spreadsheet.ActiveSheet.Range["A5"].Hyperlinks.RemoveAt(0);
spreadsheet.ActiveGrid.InvalidateCell(GridRangeInfo.Cell(5,1));

{% endhighlight %}
{% endtabs %}
