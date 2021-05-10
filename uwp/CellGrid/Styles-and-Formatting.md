---
layout: post
title: Styles and Formatting in UWP CellGrid control | Syncfusion
description: Learn here all about Styles and Formatting support in Syncfusion UWP CellGrid (SfCellGrid) control and more.
platform: uwp
control: SfCellGrid
documentation: ug
---

# Styles and Formatting in UWP CellGrid (SfCellGrid)

This section explains about some of the `GridStyleInfo` properties which customizes the `SfCellGrid` and its inner elements(cell,row, column..)

## GridStyleInfo Overview

SfCellGrid is a tabular representation of grid cells which contains data. Each cell contains unique information and can be displayed independently of other cells. 
`GridStyleInfo` objects are used to store information the appearance of a grid cell. So the attributes like Font, Background, Border,Alignment, CellValue and CellType etc. are all reflected in a single `GridStyleInfo` object. 

Every cell in a `SfCellGrid` may have such an object associated with it, giving the individual cell its unique appearance. It is not necessary that all cells should require fully populated `GridStyleInfo` objects stored in memory to function.

## Cell Background

The `Background` property of `GridStyleInfo` class specifies the background brush color for the cells or entire grid.

{% tabs %}
{% highlight c# %}

//To apply the background for particular cell,
this.cellGrid.Model[2, 2].Background = new SolidColorBrush(Colors.Green);

//To apply background for header cells alone,
cellGrid.Model.HeaderStyle.Background = new SolidColorBrush(Colors.Yellow);

//To apply the background for the entire grid,
cellGrid.Model.TableStyle.Background = new SolidColorBrush(Colors.LightPink);

//To apply the background for the footer cells alone,
cellGrid.Model.FooterStyle.Background = new SolidColorBrush(Colors.GreenYellow);

//To apply the background for the particular column,
cellGrid.Model.ColStyles[4].Background = new SolidColorBrush(Colors.Blue);

//To apply the background for the particular row,
cellGrid.Model.RowStyles[3].Background = new SolidColorBrush(Colors.Almond);

{% endhighlight %}
{% endtabs %} 

## Cell Foreground

The `Foreground` property of `GridStyleInfo` class specifies the foreground brush color for the value or text in the cells or entire grid.

{% tabs %}
{% highlight c# %}

//To apply the foreground for particular cell,
this.cellGrid.Model[2, 2].Foreground = new SolidColorBrush(Colors.Green);

//To apply foreground for header cells alone,
cellGrid.Model.HeaderStyle.Foreground = new SolidColorBrush(Colors.Yellow);

//To apply the foreground for the entire grid,
cellGrid.Model.TableStyle.Foreground = new SolidColorBrush(Colors.LightPink);

//To apply the foreground for the footer cells alone,
cellGrid.Model.FooterStyle.Foreground = new SolidColorBrush(Colors.GreenYellow);

//To apply the foreground for the particular column,
cellGrid.Model.ColStyles[4].Foreground = new SolidColorBrush(Colors.Blue);

//To apply the foreground for the particular row,
cellGrid.Model.RowStyles[3].Foreground = new SolidColorBrush(Colors.Almond);

{% endhighlight %}
{% endtabs %} 

## Font

The `Font` property of the `GridStyleInfo` class specifies the font for the text displayed in the cell. In SfCellGrid, `GridFontInfo` class contains all the attributes related with font styles.

{% tabs %}
{% highlight c# %}

cellGrid.Model[3, 3].Font.FontSize = 20;
cellGrid.Model[3, 3].Font.FontStretch = FontStretch.SemiCondensed;
cellGrid.Model[3, 3].Font.FontStyle = FontStyle.Italic;
cellGrid.Model[3, 3].Font.FontWeight = FontWeights.Bold;
cellGrid.Model[3, 3].Font.FontFamily = new FontFamily("Times New Roman");

{% endhighlight %}
{% endtabs %}

## CellValue

Value for the cells can be changed by using `CellValue` property. 

{% tabs %}
{% highlight c# %}

//To assign the cell value for particular cell,
cellGrid.Model[3, 3].CellValue = "Syncfusion";

//To assign the cell value for header cells alone,
cellGrid.Model.HeaderStyle.CellValue = "Syncfusion";

//To assign the cell value for the entire grid,
cellGrid.Model.TableStyle.CellValue = "Syncfusion";

//To assign the cell value for the footer cells alone,
cellGrid.Model.FooterStyle.CellValue = "Syncfusion";

//To assign the cell value for the particular column,
cellGrid.Model.ColStyles[4].CellValue = "Syncfusion");

//To assign the cell value for the particular row,
cellGrid.Model.RowStyles[3].CellValue = "Syncfusion";

{% endhighlight %}
{% endtabs %} 

## Cell Alignment

To set the horizontal and vertical alignment to the text in a cell, `HorizontalAlignment` and `VerticalAlignment` properties are used.

{% tabs %}
{% highlight c# %}

cellGrid.Model[3, 3].HorizontalAlignment = HorizontalAlignment.Center;
cellGrid.Model[3, 3].VerticalAlignment = VerticalAlignment.Bottom;

{% endhighlight %}
{% endtabs %} 

## Borders

Borders can be set on all sides of a cell by setting `Borders` property. Cell borders can be customized to have different color, thickness and style. It is possible to have 
different border styles for top, bottom, left and right borders for the same cell.

### To apply border styles for particular range

{% tabs %}
{% highlight c# %}

//Apply same border style to all sides,
cellGrid.Model[3, 3].Borders.All = new Pen(new SolidColorBrush(Colors.Green), 2, BorderStyle.DashDotDot);

//Apply different border styles to each sides,
cellGrid.Model[2, 2].Borders.Top = new Pen(new SolidColorBrush(Colors.Pink), 2, BorderStyle.Dashed);
cellGrid.Model[2, 2].Borders.Bottom = new Pen(new SolidColorBrush(Colors.Yellow), 4, BorderStyle.Dotted);
cellGrid.Model[2, 2].Borders.Left = new Pen(new SolidColorBrush(Colors.AliceBlue), 2, BorderStyle.Standard);
cellGrid.Model[2, 2].Borders.Right = new Pen(new SolidColorBrush(Colors.Blue), 3, BorderStyle.DashDot);

{% endhighlight %}
{% endtabs %} 

### To apply border styles for the group of cells

{% tabs %}
{% highlight c# %}

//To apply border styles for header cells alone,
cellGrid.Model.HeaderStyle.Borders.All = new Pen(new SolidColorBrush(Colors.Green), 2, BorderStyle.DashDotDot);

//To assign the cell value for the entire grid,
cellGrid.Model.TableStyle.Borders.All = new Pen(new SolidColorBrush(Colors.Green), 2, BorderStyle.DashDotDot);

//To assign the cell value for the footer cells alone,
cellGrid.Model.FooterStyle.Borders.All = new Pen(new SolidColorBrush(Colors.Green), 2, BorderStyle.DashDotDot);

//To assign the cell value for the particular column,
cellGrid.Model.ColStyles[4].Borders.All = new Pen(new SolidColorBrush(Colors.Green), 2, BorderStyle.DashDotDot);

//To assign the cell value for the particular row,
cellGrid.Model.RowStyles[3].Borders.All = new Pen(new SolidColorBrush(Colors.Green), 2, BorderStyle.DashDotDot);

{% endhighlight %}
{% endtabs %} 

## Format

The formats of a cell value can be changed by using `Format` property. SfCellGrid allows you to apply different formatting types to the cell values. For more details on the different types of formatting types, please check the MSDN link over [here.](https://msdn.microsoft.com/en-us/library/26etazsy.aspx)

{% tabs %}
{% highlight c# %}

//To apply LongDate pattern to the cell value,

cellGrid.Model[2, 2].CellValue = "234234";
cellGrid.Model[2, 2].Format = "D";

{% endhighlight %}
{% endtabs %} 

## Text Wrap

If the cell value in the SfCellGrid does not fit in a single line, then it can be wrapped by using `TextWrapping` property and the height can be adjusted with
`ResizeRowsToFit` method.

{% tabs %}
{% highlight c# %}

public MainPage()
{   
    cellGrid.Model[2, 2].CellValue = "Syncfusion wrap text testing in a cell";
	
	//To wrap the text in a cell,
    cellGrid.Model[2, 2].TextWrapping= TextWrapping.Wrap;
	
    cellGrid.Loaded += CellGrid_Loaded;
}

private void CellGrid_Loaded(object sender, RoutedEventArgs e)
{   
	//To adjust height based on word wrap,        
    cellGrid.Model.ResizeRowsToFit(GridRangeInfo.Row(2), GridResizeToFitOptions.None);           
}

{% endhighlight %}
{% endtabs %} 

## Text Trim

When the text exceeds the edge of the cell in SfCellGrid, it can be trimmed by using `TextTrimming` property.

{% tabs %}
{% highlight c# %}

//To trim the text in a cell,

cellGrid.Model[3, 3].TextTrimming = TextTrimming.Clip;
cellGrid.Model[3, 3].CellValue = "Syncfusion text trimming test in cell";

{% endhighlight %}
{% endtabs %} 

T> If you want to apply the styles at runtime, you can use [QueryCellInfo](http://help.syncfusion.com/uwp/sfcellgrid/working-with-sfcellgrid#querycellinfo-event) Event.

## Clearing styles 

To remove the `GridStyleInfo` properties along with the data in SfCellGrid, `ClearStyle` and `ClearStyles` methods are used.

{% tabs %}
{% highlight c# %}

//To clear style in particular cell,
cellGrid.Model.ClearStyle(new RowColumnIndex(3, 3));

//To clear all the styles in the entire grid,
cellGrid.Model.ClearStyles();

{% endhighlight %}
{% endtabs %} 

N> Users need to invalidate the cells using `InvalidateCell(rowIndex,colIndex)` method, if the formatting is applied at runtime like button click event. For more info, please refer [here](http://help.syncfusion.com/uwp/sfcellgrid/working-with-sfcellgrid#refreshing-the-grid).
