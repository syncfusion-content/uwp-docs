---
layout: post
title: Area | SfChart | uwp | Syncfusion
description: area
platform: uwp
control: SfChart
documentation: ug
---

# Area	

Chart area represents the entire chart and all its elements. It’s a virtual rectangular area that includes all the chart elements like axis, legends, series etc. 

The following are the major properties of chart(SfChart):

* [`PrimaryAxis`](http://help.syncfusion.com/uwp/sfchart/axis) –  Gets or sets the horizontal x axis for the chart.
* [`SecondaryAxis`](http://help.syncfusion.com/uwp/sfchart/axis) –  Gets or sets the vertical y axis for the chart.
* [`Legend`](http://help.syncfusion.com/uwp/sfchart/legend) –  Gets or sets the legend for the chart.
* [`Series`](http://help.syncfusion.com/uwp/sfchart/series) –  Gets or sets the list of series in the chart.
* [`TechnicalIndicators`](http://help.syncfusion.com/uwp/sfchart/technical-indicators) –  Gets or sets the various financial indicators for the chart.
* [`Behaviors`](http://help.syncfusion.com/uwp/sfchart/interactive-features)–  Used to add one more interactive features to the chart.

## Chart Header

Header property is used to define the title for the chart. This allows you to add any object (.Net object) as content for chart title. 

{% highlight xaml %}

<syncfusion:SfChart  Header="Usage of Metals" />

{% endhighlight %}

![SfChart with header.](Area_images/Area_img1.jpeg)


Header can be positioned left or right side of the chart using `HorizontalHeaderAlignment` property.

Also you can add more customization for the header as below: 

{% highlight xaml %}

<chart:SfChart.Header>

<Border BorderThickness="0.5" BorderBrush="Black" Margin="10" CornerRadius="5">

<TextBlock FontSize="14" Text="Chart Area Header" Margin="5">

<TextBlock.Effect>

<DropShadowEffect Color="Black" 

Opacity="0.5" />

</TextBlock.Effect>

</TextBlock>

</Border>

</chart:SfChart.Header>

{% endhighlight %}

![Header customization in SfChart](Area_images/Area_img2.jpeg)


N> Here, HorizontalHeaderAlignment is set as ‘Right’.

## Area Customization

SfChart provides the properties like `AreaBorderBrush`, `AreaBorderThickness`, `AreaBackground` and `Background` for customizing the plot area.

The following code examples illustrates the usage of these properties:

{% highlight xaml %}

<chart:SfChart Height="250" Width="350" 

Header="Chart Area Header" 

AreaBackground="Cyan" 

Background="LightGray" 

AreaBorderBrush="Gray" 

AreaBorderThickness="3" >

{% endhighlight %}

![SfChart with customized plot area](Area_images/Area_img3.jpeg)


## Multiple Area 

You can split plot area into multiple rows and columns using `ChartRowDefinition` and `ChartColumnDefinition` like Grid panel’s row and column definition. 

The following code example demonstrates, how you can create multiple panes in the chart area:

{% highlight xaml %}

<chart:SfChart >

<!--Adding row definition to the chart-->

<chart:SfChart.RowDefinitions>

<chart:ChartRowDefinition/>

<chart:ChartRowDefinition/>

</chart:SfChart.RowDefinitions>

<!--Adding column definition to the chart-->

<chart:SfChart.ColumnDefinitions>

<chart:ChartColumnDefinition/>

<chart:ChartColumnDefinition/>

</chart:SfChart.ColumnDefinitions>

<chart:SfChart.PrimaryAxis>

<chart:CategoryAxis chart:ChartBase.ColumnSpan="2"/>

</chart:SfChart.PrimaryAxis>



<chart:SfChart.SecondaryAxis>

<chart:NumericalAxis  PlotOffset="13" chart:ChartBase.ColumnSpan="2" />

</chart:SfChart.SecondaryAxis>



<chart:ColumnSeries Palette="LightCandy"

ItemsSource="{Binding SneakersDetail}"         

XBindingPath="Brand" 

YBindingPath="ItemsCount1" 

/>

<chart:ColumnSeries Palette="Metro"

ItemsSource="{Binding SneakersDetail}"  

XBindingPath="Brand" 

YBindingPath="ItemsCount" 

>

<chart:ColumnSeries.YAxis>

<chart:NumericalAxis  PlotOffset="10"

chart:SfChart.Row="1" >

</chart:NumericalAxis>

</chart:ColumnSeries.YAxis>

</chart:ColumnSeries>

</chart:SfChart>

{% endhighlight %}

![SfChart with multiple panes](Area_images/Area_img4.jpeg)


## Column Span and Row Span

These can be used to specify the number of column or rows up to which the axis can extend. Same like Grid’s RowSpan or ColumnSpan property, it is also an attached property.

You can set the row span in chart like the following code example.

{% highlight xaml %}

<chart:SfChart>

<!--Adding row definition to the chart-->

<chart:SfChart.RowDefinitions>

<chart:ChartRowDefinition/>

<chart:ChartRowDefinition/>

</chart:SfChart.RowDefinitions>

<chart:SfChart.PrimaryAxis>

<chart:CategoryAxis   chart:ChartBase.RowSpan="2" 

chart:SfChart.Row="0"

TickLinesPosition="Outside">                                                              

</chart:CategoryAxis>

</chart:SfChart.PrimaryAxis>

<chart:SfChart.SecondaryAxis>

<chart:NumericalAxis />

</chart:SfChart.SecondaryAxis>

<chart:ColumnSeries XBindingPath="Brand"

ItemsSource="{Binding SneakersDetail}"  

YBindingPath="ItemsCount1" 

/>



<chart:LineSeries Interior="CadetBlue" XBindingPath="Brand"

ItemsSource="{Binding SneakersDetail}"   

YBindingPath="ItemsCount">

<chart:LineSeries.YAxis>

<chart:NumericalAxis chart:ChartBase.RowSpan="2">

</chart:NumericalAxis>

</chart:LineSeries.YAxis>              

</chart:LineSeries>

</chart:SfChart>

{% endhighlight %}

![SfChart with two y axes, one axis spanned to two rows](Area_images/Area_img5.jpeg)


## Placing Series Side-By-Side

It defines the placement pattern of bar type series like Column, Bar, RangeColumn, etc. 

It is a Boolean property and its default value is true so the segment will be placed adjacent to each other (Clustered).

![Column chart type placed side by side](Area_images/Area_img6.jpeg)


The following code example and image illustrates the placement of series while setting `SideBySideSeriesPlacement` as false.

{% highlight xaml %}

<chart:SfChart x:Name="columnChart" AreaBorderBrush="DarkGray" 

Header="Usage of Metals"  

SideBySideSeriesPlacement="False"

AreaBorderThickness="1,1,1,1">

<chart:SfChart.PrimaryAxis>

<chart:CategoryAxis  Header="Metals"/>

</chart:SfChart.PrimaryAxis>

<chart:SfChart.SecondaryAxis>

<chart:NumericalAxis Header="Usage" />                            

</chart:SfChart.SecondaryAxis>

<chart:SfChart.Legend>

<chart:ChartLegend Visibility="Visible" />

</chart:SfChart.Legend>

<chart:ColumnSeries Interior="#bcbcbc"

ItemsSource="{Binding SneakersDetail}" Label="2015"  

XBindingPath="Brand" 

YBindingPath="ItemsCount" />

<chart:ColumnSeries ItemsSource="{Binding SneakersDetail}"  

SegmentSpacing="0.5"

Interior="#4a4a4a"  XBindingPath="Brand" 

Label="2014" YBindingPath="postion"/>            

</chart:SfChart>

{% endhighlight %}

{% highlight C# %}

{% endhighlight %}

![Column chart type place one over another.](Area_images/Area_img7.jpeg)


N>As the series will be placed one over the other(overlapped), to differentiate between the series the `SegmentSpacing` is used.

## Serialization

SfChart supports serialization and deserialization for save the settings of the chart and reload. 

This can be done using `Serialize` and `Deserialize` methods as in below code example:

{% highlight xaml %}

<chart:SfChart Margin="10" x:Name="chart" Header="Defect Rates">

<chart:SfChart.Annotations>

<chart:RectangleAnnotation X1="0" X2="2" Y1="20" Y2="30" CanDrag="True" CanResize="True"/>

</chart:SfChart.Annotations>



<chart:SfChart.PrimaryAxis>

<chart:CategoryAxis Header="X Axis" />

</chart:SfChart.PrimaryAxis>



<chart:SfChart.SecondaryAxis>

<chart:NumericalAxis Header="Y Axis" />

</chart:SfChart.SecondaryAxis>



<chart:ColumnSeries ItemsSource="{Binding CategoricalDatas}" XBindingPath="Category"

YBindingPath="Value"  >

</chart:ColumnSeries>

</chart:SfChart>

{% endhighlight %}

{% highlight xml %}

Serialized Chart

<SfChart Watermark="{x:Null}" Header="Defect Rates" Name="chart" Margin="10,10,10,10" xmlns="http://schemas.syncfusion.com/wpf" xmlns:av="http://schemas.microsoft.com/winfx/2006/xaml/presentation" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">

<SfChart.PrimaryAxis>

<CategoryAxis LabelRotationAngle="0" Header="X Axis" Width="566.466666666667" av:Canvas.Left="49.5333333333333" av:Canvas.Top="183.82">

<CategoryAxis.StripLines>

<ChartStripLines />

</CategoryAxis.StripLines>

</CategoryAxis>

</SfChart.PrimaryAxis>

<SfChart.SecondaryAxis>

<NumericalAxis LabelRotationAngle="0" Header="Y Axis" Height="183.82" av:Canvas.Left="0" av:Canvas.Top="0">

<NumericalAxis.StripLines>

<ChartStripLines />

</NumericalAxis.StripLines>

</NumericalAxis>

</SfChart.SecondaryAxis>

<SfChart.Behaviors>

<ChartBehaviorsCollection />

</SfChart.Behaviors>

<SfChart.Annotations>

<AnnotationCollection>

<RectangleAnnotation CanDrag="True" CanResize="True" Y2="30" X2="2" X1="0" Y1="20" />

</AnnotationCollection>

</SfChart.Annotations>

<SfChart.ColumnDefinitions>

<ChartColumnDefinition />

</SfChart.ColumnDefinitions>

<SfChart.RowDefinitions>

<ChartRowDefinition />

</SfChart.RowDefinitions>

<ColumnSeries YBindingPath="Value" ItemsSource="{av:Binding Path=CategoricalDatas}" XBindingPath="Category" xmlns="http://schemas.syncfusion.com/wpf" xmlns:av="http://schemas.microsoft.com/winfx/2006/xaml/presentation">

<ColumnSeries.Trendlines>

<ChartTrendLineCollection />

</ColumnSeries.Trendlines>

<ColumnSeries.LegendIconTemplate>

<av:DataTemplate>

<av:Rectangle Stretch="Fill" Fill="{av:Binding Path=Interior}" Stroke="{av:Binding Path=Stroke}" StrokeThickness="{av:Binding Path=StrokeThickness}" />

</av:DataTemplate>

</ColumnSeries.LegendIconTemplate>

<ColumnSeries.Clip>

<av:RectangleGeometry Rect="0,0,566.966666666667,184.32" />

</ColumnSeries.Clip>

</ColumnSeries>

</SfChart>

{% endhighlight %}

## Clone or copy the chart

More like serialization, you can use `Clone` method for SfChart control state persistence. This method creates a copy of the chart instance.

{% highlight C# %}

var chartCopy = chart.Clone() as SfChart;

grid.Children.Add(chartCopy as SfChart);

//Here, 'grid' is an empty container in the application to hold the chart. 

{% endhighlight %}

T> You can use this method for copy and paste like requirement, by cloning chart upon copy and reload while pasting.

## Deferred real-time updates

You can hold and resume the series updates in dynamic update scenarios using the below methods.

`SuspendSeriesNotification`

`ResumeSeriesNotification`


## Chart events

SfChart provides the following list of events.

* [`SelectionChanging`](http://help.syncfusion.com/uwp/sfchart/interactive-features#selection)

* [`SelectionChanged`](http://help.syncfusion.com/uwp/sfchart/interactive-features#selection)

* [`ZoomChanging`](http://help.syncfusion.com/uwp/sfchart/interactive-features#zooming-and-panning)

* [`ZoomChanged`](http://help.syncfusion.com/uwp/sfchart/interactive-features#zooming-and-panningg)

* [`SelectionZoomingStart`](http://help.syncfusion.com/uwp/sfchart/interactive-features#zooming-and-panning)

* [`SelectionZoomingEnd`](http://help.syncfusion.com/uwp/sfchart/interactive-features#zooming-and-panning)

* [`SelectionZoomingDelta`](http://help.syncfusion.com/uwp/sfchart/interactive-features#zooming-and-panning)

* [`PanChanging`](http://help.syncfusion.com/uwp/sfchart/interactive-features#zooming-and-panning)

* [`PanChanged`](http://help.syncfusion.com/uwp/sfchart/interactive-features#zooming-and-panning)

* [`ResetZooming`](http://help.syncfusion.com/uwp/sfchart/interactive-features#zooming-and-panning)

**See also**

`PointToValue`

`ValueToPoint`

