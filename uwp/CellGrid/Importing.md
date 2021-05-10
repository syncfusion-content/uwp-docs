---
layout: post
title: Importing in UWP CellGrid control | Syncfusion
description: Learn here all about Importing support in Syncfusion UWP CellGrid (SfCellGrid) control and more.
platform: uwp
control: SfCellGrid
documentation: ug
---

# Importing in UWP CellGrid (SfCellGrid)

The `ExcelImportExtension` class is used to import entire cells from the Excel sheet to SfCellGrid. 

Following styles are imported from Excel:

* Font
* Back color and fore color
* Alignment
* Borders
* Number formats
* Merge cells
* Row height
* Column width
* Freeze panes
* Orientation
* Conditional formats

## ExcelImportingOptions

The `ExcelImportingOptions` is added as second parameter when importing from Excel. Various importing modes are value, style, and text. Default `ImportMode` is `Value`.

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

## Using stream

The SfCellGrid provides support to import the data from Excel using the `ImportFromExcel` method by passing the Excel file as `Stream`.

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

## Using worksheet

The SfCellGrid provides support to import the data from Excel using the `ImportFromExcel` method by passing the worksheet(`IWorksheet`) from XlsIO.

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

## Using storage file

The SfCellGrid provides support to import the data from Excel using the `ImportFromExcel` method by passing the Excel file as `StorageFile`.

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
