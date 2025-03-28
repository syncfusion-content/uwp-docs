---
layout: post
title: Shapes in UWP Spreadsheet control | Syncfusion®
description: Learn here all about Shapes support in Syncfusion® UWP Spreadsheet (SfSpreadsheet) control and more.
platform: UWP
control: SfSpreadsheet
documentation: ug
---

# Shapes in UWP Spreadsheet (SfSpreadsheet)
  This section explains about importing of charts, sparklines, pictures and textboxes in SfSpreadsheet.

## Charts

SfSpreadsheet provides support to import charts from excel which are used to represent numeric data in graphical format to make it easier to understand large quantities of data.

For importing charts in SfSpreadsheet, add the following assembly as reference into the application.
 
Assembly: **Syncfusion.SfSpreadsheetHelper.UWP.dll**  

Create an instance of `Syncfusion.UI.Xaml.SpreadsheetHelper.GraphicChartCellRenderer` and add that renderer into `GraphicCellRenderers` collection by using the helper method `AddGraphicChartCellRenderer` which is available under the namespace `Syncfusion.UI.Xaml.Spreadsheet.GraphicCells`. 

{% tabs %}
{% highlight c# %}

public MainWindow()
{
  InitializeComponent();
  
  //For importing charts,
  this.spreadsheet.AddGraphicChartCellRenderer(new GraphicChartCellRenderer());
}

{% endhighlight %}
{% endtabs %}

### Adding the Charts at runtime

For adding the Charts in SfSpreadsheet at runtime, use `AddChart` method, also you can resize and reposition the chart.

{% tabs %}
{% highlight c# %}

var chart = spreadsheet.AddChart(spreadsheet.ActiveSheet);

object[] Y_values = new object[] { 200, 100, 100 };
object[] X_values = new object[] { "Total Income", "Expenses", "Profit" };

IChartSerie series = chart.Series.Add(ExcelChartType.Pie);

// Enters the X and Y values directly
series.EnteredDirectlyValues = Y_values;
series.EnteredDirectlyCategoryLabels = X_values;

var shape = chart as ShapeImpl;

// Re-Positioning Chart
shape.Top = 200;
shape.Left = 200;

//Re-sizing a Chart
shape.Height = 300;
shape.Width = 300;
{% endhighlight %}
{% endtabs %}


## Sparklines

For importing sparklines in SfSpreadsheet, add the following assembly as reference into the application.
 
Assembly: **Syncfusion.SfSpreadsheetHelper.UWP.dll**  

Create an instance of `Syncfusion.UI.Xaml.SpreadsheetHelper.SparklineCellRenderer` and add that renderer into the Spreadsheet by using the helper method `AddSparklineCellRenderer` which is available under the namespace `Syncfusion.UI.Xaml.Spreadsheet.GraphicCells`.

{% tabs %}
{% highlight c# %}

public MainWindow()
{
  InitializeComponent();
      
  //For importing sparklines,
  this.spreadsheet.AddSparklineCellRenderer(new SparklineCellRenderer());
}

{% endhighlight %}
{% endtabs %}

## Pictures

SfSpreadsheet provides support to import images in SpreadsheetGrid and to add an image at run time, use `AddImage` method and also you can resize and reposition the image.

{% tabs %}
{% highlight c# %}

var worksheet = spreadsheet.ActiveSheet;
var stream = typeof(MainWindow).Assembly.GetManifestResourceStream("GraphicCellDemo.Data.Sample.jpg");
var shape = spreadsheet.AddImage(worksheet, new RowColumnIndex(5, 5), stream);

// Re-Positioning Picture
shape.Top = 200;
shape.Left = 200;

 //Re-sizing a Picture
shape.Height = 200;
shape.Width = 200;

{% endhighlight %}
{% endtabs %}


## Text Boxes

SfSpreadsheet provides support to import RichText Box in SpreadsheetGrid and to add the rich text box at run time, use `AddTextBox` method

{% tabs %}
{% highlight c# %}

var rtfText = "{\\rtf1\\ansi\\ansicpg1252\\deff0\\deflang1033{\\fonttbl{\\f0\\fnil\\fcharset1 Calibri;}{\\f1\\fnil\\fcharset1 Calibri;}}{\\colortbl;\\red0\\green0\\blue0;\\red255\\green0\\blue0;}{\\f0\\fs22\\b\\cf1\\u83*\\u121*\\u110*\\u99*\\u102*\\u117*\\u115*\\u105*\\u111*\\u110*\\u32*\\b0}                           {\\f1\\fs22\\cf2\\u83*\\u111*\\u102*\\u116*\\u119*\\u97*\\u114*\\u101*\\u32*}{\\f1\\fs22\\cf1\\u80*\\u118*\\u116*\\u46*\\u32*\\u76*\\u116*\\u100*}}";
var textBox = spreadsheet.AddTextBox(spreadsheet.ActiveSheet, new RowColumnIndex(5, 5), new Size(200, 200), rtfText) as TextBoxShapeImpl;

// Re-positioning RichTextBox
textBox.Left = 200;
textBox.Top = 200;
         
{% endhighlight %}
{% endtabs %}

## Accessing the selected Shapes

SfSpreadsheet allows the user to access the selected shapes and modify the properties associated with it in `SpreadsheetGrid`.

{% tabs %}
{% highlight c# %}

var selectedShape = spreadsheet.ActiveGrid.GraphicModel.SelectedShapes;

for(int i = 0; i < selectedShape.Count ; i++)
{

    if(ExcelShapeType.Chart == selectedShape[i].ShapeType)
    {
        var chart = selectedShape[i] as IChart;
        chart.ChartArea.Fill.FillType = ExcelFillType.Gradient;
        chart.ChartArea.Fill.ForeColor = Color.Blue;
    }

    else if(ExcelShapeType.Picture == selectedShape[i].ShapeType)
    {
        var picture = selectedShape[i] as ShapeImpl;
        picture.Height = 100;
        picture.Width = 100;
    }
}
spreadsheet.ActiveGrid.GraphicModel.InvalidateGraphicObjects();
spreadsheet.ActiveGrid.GraphicModel.InvalidateGraphicVisual();

{% endhighlight %}
{% endtabs %}

## Select a Shape Programmatically

Users can select a shape programmatically by using `AddSelectedShapes` method of `GraphicModel` class.

{% tabs %}
{% highlight c# %}

var shape = spreadsheet.ActiveSheet.Shapes[2] as ShapeImpl;          
spreadsheet.ActiveGrid.GraphicModel.AddSelectedShapes(shape);

{% endhighlight %}
{% endtabs %}

## Clear a Selection

Users can clear the selection from the shapes and move the selection to the grid using `ClearSelection` method of `GraphicModel` class.

{% tabs %}
{% highlight c# %}

spreadsheet.ActiveGrid.GraphicModel.ClearSelection();

{% endhighlight %}
{% endtabs %}
