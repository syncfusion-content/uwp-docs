---
layout: post
title: Importing
description: How to import the data from excel in SfCellGrid
platform: uwp
control: SfCellGrid
documentation: ug
---

# Import

The `ExcelImportExtension` class is used to import the entire cells from Excel sheet to SfCellGrid. 

The following styles are imported from Excel,

* Font
* Back color and Fore color
* Alignment
* Borders
* Number Formats
* Merge cells
* Row height
* Column width
* Freeze panes
* Orientation
* Conditional Formats

## ExcelImportingOptions

`ExcelImportingOptions` is added as second parameter while importing from excel. It sets the importing mode, such as Value, Style and Text. Default `ImportMode` is `Value`.

{% tabs %}
{% highlight c# %}

//Imports style and text from excel
ExcelImportingOptions option = new ExcelImportingOptions();
option.ImportMode = ImportMode.Value;

//Imports style only from excel
ExcelImportingOptions option = new ExcelImportingOptions();
option.ImportMode = ImportMode.Style;

//Imports text only from excel
ExcelImportingOptions option = new ExcelImportingOptions();
option.ImportMode = ImportMode.Text;

{% endhighlight %}
{% endtabs %}

## Using Stream

SfCellGrid provides support to import the data from Excel using `ImportFromExcel` method by passing the excel file as `Stream`.

{% tabs %}
{% highlight c# %}

//Import using stream,
var assembly = typeof(MainPage).GetTypeInfo().Assembly;
string resourcePath = "SampleApp.Assets.Book1.xlsx";
var fileStream = assembly.GetManifestResourceStream(resourcePath);
cellGrid.ImportFromExcel(fileStream);	


//Import using stream with importing option,
var assembly = typeof(MainPage).GetTypeInfo().Assembly;
string resourcePath = "SampleApp.Assets.Book1.xlsx";
ExcelImportingOptions option = new ExcelImportingOptions();
option.ImportMode = ImportMode.Style;
var fileStream = assembly.GetManifestResourceStream(resourcePath);
cellGrid.ImportFromExcel(fileStream,option);	

{% endhighlight %}
{% endtabs %}

## Using Worksheet

SfCellGrid provides support to import the data from Excel using `ImportFromExcel` method by passing the worksheet(`IWorksheet`) from XlsIO.

{% tabs %}
{% highlight c# %}

//Import using Worksheet from XlsIO,
var assembly = typeof(MainPage).GetTypeInfo().Assembly;
string resourcePath = "SampleApp.Assets.Book1.xlsx";
var fileStream = assembly.GetManifestResourceStream(resourcePath);
ExcelEngine engine = new ExcelEngine();
var workbook = engine.Excel.Application.Workbooks.OpenAsync(fileStream);
cellGrid.ImportFromExcel((workbook as IWorkbook).ActiveSheet);	

//Import using Worksheet from XlsIO with importing option,
var assembly = typeof(MainPage).GetTypeInfo().Assembly;
string resourcePath = "SampleApp.Assets.Book1.xlsx";
ExcelImportingOptions option = new ExcelImportingOptions();
option.ImportMode = ImportMode.Style;
var fileStream = assembly.GetManifestResourceStream(resourcePath);
ExcelEngine engine = new ExcelEngine();
var workbook = engine.Excel.Application.Workbooks.OpenAsync(fileStream);
cellGrid.ImportFromExcel((workbook as IWorkbook).ActiveSheet,option);

{% endhighlight %}
{% endtabs %}

## Using Storage File

SfCellGrid provides support to import the data from Excel using `ImportFromExcel` method by passing the excel file as `StorageFile`.

{% tabs %}
{% highlight c# %}

//Import using Storage File,
FileOpenPicker filePicker = new FileOpenPicker();
filePicker.ViewMode = PickerViewMode.List;
filePicker.SuggestedStartLocation = PickerLocationId.Desktop;
filePicker.FileTypeFilter.Add(".xls");
filePicker.FileTypeFilter.Add(".xlsx");

StorageFile file = await filePicker.PickSingleFileAsync();
cellGrid.ImportFromExcel(file);

//Import using Storage File along with importing option,
FileOpenPicker filePicker = new FileOpenPicker();
filePicker.ViewMode = PickerViewMode.List;
filePicker.SuggestedStartLocation = PickerLocationId.Desktop;
filePicker.FileTypeFilter.Add(".xls");
filePicker.FileTypeFilter.Add(".xlsx");

//Setting the Excel importing option,
ExcelImportingOptions option = new ExcelImportingOptions();
option.ImportMode = ImportMode.Value;

StorageFile file = await filePicker.PickSingleFileAsync();
cellGrid.ImportFromExcel(file, option);

{% endhighlight %}
{% endtabs %}

