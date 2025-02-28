---
layout: post
title: Cell Styles in UWP CellGrid control | Syncfusion®
description: Learn here all about Cell Styles support in Syncfusion® UWP CellGrid (SfCellGrid) control and more.
platform: uwp
control: SfCellGrid
documentation: ug
---

# Cell Styles in UWP CellGrid (SfCellGrid)

This section explains about how to apply the cell styles to customize the appearance in SfCellGrid.

## BaseStyles

BaseStyles is one of the parent-type style which is used to customize the cell’s appearance. BaseStyles are `GridStyleInfo` objects which can be associated with an arbitrary collection of cells. 

{% tabs %}
{% highlight c# %}

GridStyleInfo baseStyle = cellGrid.Model.BaseStylesMap["custom"].StyleInfo;
baseStyle.Background = new SolidColorBrush(Colors.Green);
baseStyle.Foreground = new SolidColorBrush(Colors.Red);
baseStyle.Font.FontStyle = FontStyle.Italic;

cellGrid.Model[5,3].BaseStyle = "custom";
            
{% endhighlight %}
{% endtabs %} 
          
### QueryBaseStyle Event

 `QueryBaseStyle` Event is used to apply the `BaseStyle` at run time in SfCellGrid instead of storing in the base style collection.
 
{% tabs %}
{% highlight c# %}

 //BaseStyle 1
GridStyleInfo baseStyle = cellGrid.Model.BaseStylesMap["custom"].StyleInfo;
baseStyle.Background = new SolidColorBrush(Colors.Green);
baseStyle.Foreground = new SolidColorBrush(Colors.Red);
baseStyle.CellValue = "BaseStyle1";
baseStyle.Font.FontStyle = FontStyle.Italic;

//BaseStyle 2
GridStyleInfo baseStyle1 = cellGrid.Model.BaseStylesMap["custom1"].StyleInfo;
baseStyle1.Background = new SolidColorBrush(Colors.Orange);
baseStyle1.Foreground = new SolidColorBrush(Colors.Magenta);
baseStyle1.Font.FontSize = 12;
baseStyle1.CellValue = "BaseStyle2";
baseStyle1.Font.FontWeight = FontWeights.ExtraBold;

this.cellGrid.Model.QueryBaseStyles += Model_QueryBaseStyles

//Assigning styles at runtime through  QueryBaseStyle event

private void Model_QueryBaseStyles(object sender, Syncfusion.UI.Xaml.CellGrid.Styles.GridQueryBaseStylesEventArgs e)
{
    if (e.Cell.RowIndex >5 && e.Cell.ColumnIndex < 15)
        e.Style.BaseStyle = "custom";
    if (e.Cell.RowIndex < 4 && e.Cell.ColumnIndex < 15)
        e.Style.BaseStyle = "custom1";
}
            
{% endhighlight %}
{% endtabs %} 

## TableStyle

TableStyle is a single `GridStyleInfo` object that is associated with the entire grid. To apply the styles for the each and every cell in
SfCellGrid, `TableStyle` property is used

{% tabs %}
{% highlight c# %}

// Applying styles for whole grid,
cellGrid.Model.TableStyle.Background = new SolidColorBrush(Colors.LightPink);
cellGrid.Model.TableStyle.CellValue = "CellGrid";
cellGrid.Model.TableStyle.Font.FontFamily = new FontFamily("Arial");
cellGrid.Model.TableStyle.Foreground= new SolidColorBrush(Colors.SaddleBrown);
cellGrid.Model.TableStyle.Borders.All = new Pen(new SolidColorBrush(Colors.OrangeRed),2,BorderStyle.DashDotDot);

{% endhighlight %}
{% endtabs %} 

## RowStyles

RowStyles are `GridStyleInfo` objects that are associated with each row in SfCellGrid. To apply styles for particular row or range of rows, `RowStyles` property is used.

{% tabs %}
{% highlight c# %}

// Applying styles for Row 3,

cellGrid.Model.RowStyles[3].Background = new SolidColorBrush(Colors.LightPink);
cellGrid.Model.RowStyles[3].CellValue = "CellGrid";
cellGrid.Model.RowStyles[3].Font.FontFamily = new FontFamily("Arial");
cellGrid.Model.RowStyles[3].Foreground= new SolidColorBrush(Colors.SaddleBrown);
cellGrid.Model.RowStyles[3].Borders.All = new Pen(new SolidColorBrush(Colors.OrangeRed),2,BorderStyle.DashDotDot);

{% endhighlight %}
{% endtabs %}

## ColStyles

ColStyles are `GridStyleInfo` objects that are associated with each column in SfCellGrid. To apply styles for particular column or range of columns, `ColStyles` property is used.

{% tabs %}
{% highlight c# %}

//Applying Styles for Column 4,

cellGrid.Model.ColStyles[4].Background = new SolidColorBrush(Colors.GreenYellow);
cellGrid.Model.ColStyles[4].CellValue = "CellGrid";
cellGrid.Model.ColStyles[4].Font.FontFamily = new FontFamily("Verdana");
cellGrid.Model.ColStyles[4].Foreground = new SolidColorBrush(Colors.Red);
cellGrid.Model.ColStyles[4].Borders.All = new Pen(new SolidColorBrush(Colors.Gray), 2, BorderStyle.DashDotDot);

{% endhighlight %}
{% endtabs %}

N> `RowColStylePrecedence` property of `GridStyleInfo` is for setting the priority to either row/column when both `RowStyles` and `ColStyles` are used in SfCellGrid. Default `PrecedenceStyle` is Row.

## HeaderStyle

HeaderStyle are `GridStyleInfo` objects that are associated with header rows/columns in SfCellGrid. To apply styles for header rows or columns, `HeaderStyle` property is used.

{% tabs %}
{% highlight c# %}

//Setting Headers

cellGrid.HeaderRows = 2;
cellGrid.HeaderColumns = 1;
       
// Applying styles for Headers,
cellGrid.Model.HeaderStyle.Background = new SolidColorBrush(Colors.LightPink);
cellGrid.Model.HeaderStyle.CellValue = "HeaderStyle";
cellGrid.Model.HeaderStyle.Font.FontFamily = new FontFamily("Arial");
cellGrid.Model.HeaderStyle.Foreground= new SolidColorBrush(Colors.SaddleBrown);
cellGrid.Model.HeaderStyle.Borders.All = new Pen(new SolidColorBrush(Colors.OrangeRed),2,BorderStyle.DashDotDot);

{% endhighlight %}
{% endtabs %}

## FooterStyle

FooterStyle are `GridStyleInfo` objects that are associated with footer rows/columns in SfCellGrid. To apply styles for footer rows or columns, `FooterStyle` property is used.

{% tabs %}
{% highlight c# %}

//setting Footers
cellGrid.FooterRows = 2;
cellGrid.FooterColumns = 1;

//Applying Styles for Footers,
cellGrid.Model.FooterStyle.Background = new SolidColorBrush(Colors.GreenYellow);
cellGrid.Model.FooterStyle.CellValue = "FooterStyle";
cellGrid.Model.FooterStyle.Font.FontFamily = new FontFamily("Verdana");
cellGrid.Model.FooterStyle.Foreground = new SolidColorBrush(Colors.Red);
cellGrid.Model.FooterStyle.Borders.All = new Pen(new SolidColorBrush(Colors.Gray), 2, BorderStyle.DashDotDot);

{% endhighlight %}
{% endtabs %}
