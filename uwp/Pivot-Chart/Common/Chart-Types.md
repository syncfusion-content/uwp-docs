---
layout: post
title: Chart Types in UWP Pivot Chart control | Syncfusion
description: Learn here all about Chart Types support in Syncfusion® UWP Pivot Chart (SfPivotChart) control and more.
platform: UWP
control: SfPivotChart
documentation: ug
---

# Chart Types in UWP Pivot Chart (SfPivotChart)

The SfPivotChart offers different types of charts ranging from column chart to pie chart. Based on your requirements and specifications, any type of chart can be used for data visualization.

## Column charts

### Column chart

Column charts are the most common chart type that are being used for comparison analysis. It uses vertical bars (called columns) to display different values of one or more items.

The following code snippet shows how to select a simple column chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ChartType="Column"
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}"
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ChartType = PivotChartType.Column;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ChartType = PivotChartType.Column

{% endhighlight %}

{% endtabs %}

![column](Chart-Types_images/column.png)

### Stacking column chart

Stacking column charts are similar to regular column charts except that the Y values are stacked on top of each other in the specified series order. This chart helps to visualize the relationship of parts to the whole and it is widely used for proportional analysis over a particular period of time.

The following code snippet shows how to select a stacking column chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ChartType="StackingColumn"
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}"
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ChartType = PivotChartType.StackingColumn;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ChartType = PivotChartType.StackingColumn

{% endhighlight %}

{% endtabs %}

![stackingColumn](Chart-Types_images/stackingColumn.png)

### Stacking column 100 chart

Stacking column 100 chart contains stacked segments; it is a simple form of chart. In the 100 % stacked column chart, the cumulative proportion of each stacked element always totals 100%. This type of chart is used for visualizing the relative contribution of each series values to the whole.

The following code snippet shows how to select a stacking column 100 chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ChartType="StackingColumn100" 
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}"
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ChartType = PivotChartType.StackingColumn100;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ChartType = PivotChartType.StackingColumn100

{% endhighlight %}

{% endtabs %}

![stackingColumn100](Chart-Types_images/stackingColumn100.png)

## Bar charts

### Bar chart

Bar chart is the simplest and most versatile of statistical diagrams. It displays horizontal bars for each point in the series and it is widely used for comparison analysis over a particular period of time.

The following code snippet shows how to select a bar chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ChartType="Bar" 
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}"
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ChartType = PivotChartType.Bar;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ChartType = PivotChartType.Bar

{% endhighlight %}

{% endtabs %}

![bar](Chart-Types_images/bar.png)

### Stacking bar chart

Stacking bar chart is similar to stacking column chart. But, it differs from direction; it is rotated 90 degrees in clockwise direction. This type of chart is widely used for proportional analysis over a particular period of time.

The following code snippet shows how to select a stacking bar chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ChartType="StackingBar" 
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}"
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ChartType = PivotChartType.StackingBar;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ChartType = PivotChartType.StackingBar

{% endhighlight %}

{% endtabs %}

![stackingBar](Chart-Types_images/stackingBar.png)

### Stacking bar 100 chart

Stacking bar 100 chart is similar to the stacking column 100 chart. But, it differs from direction; it is rotated 90 degree in clockwise direction. This type of chart is widely used for proportional analysis over a particular period of time.

The following code snippet shows how to select a stacking bar 100 chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ChartType="StackingBar100" 
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}"
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ChartType = PivotChartType.StackingBar100;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ChartType = PivotChartType.StackingBar100

{% endhighlight %}

{% endtabs %}

![stackingbar100](Chart-Types_images/stackingbar100.png)

## Area charts

### Area chart

Area chart fills the quantitative data over a period of time. It is mainly used to compare the quantity that is plotted over two or more series.

The following code snippet shows how to select an area chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ChartType="Area" 
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}"
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ChartType = PivotChartType.Area;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ChartType = PivotChartType.Area

{% endhighlight %}

{% endtabs %}

![area](Chart-Types_images/area.png)

### Stacking area chart

Stacking area chart fills the quantitative data over a period of time like the area chart. The variation is plotting each series on the top of the previous series rather than starting from 0 in the horizontal axis. It is mainly used to compare the quantity plotted over two or more series.

The following code snippet shows how to select a stacking area chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ChartType="StackingArea" 
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}"
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ChartType = PivotChartType.StackingArea;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ChartType = PivotChartType.StackingArea

{% endhighlight %}

{% endtabs %}

![stackingArea](Chart-Types_images/stackingArea.png)

### Spline area chart

Spline area chart is mostly used to approximate the intervals with the help of spline curve. It is often used when data points are in limited number.

The following code snippet shows how to select a spline area chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ChartType="SplineArea" 
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}"
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ChartType = PivotChartType.SplineArea;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ChartType = PivotChartType.SplineArea

{% endhighlight %}

{% endtabs %}

![splineArea](Chart-Types_images/splineArea.png)

### Step area chart

In the step area chart, the points are plotted instead of a straight line tracing the shortest path between points; the values are connected by continuous vertical and horizontal lines.

The following code snippet shows how to select a step area chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ChartType="StepArea"
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}"
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ChartType = PivotChartType.StepArea;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ChartType = PivotChartType.StepArea

{% endhighlight %}

{% endtabs %}

![stepArea](Chart-Types_images/stepArea.png)

## Line charts

### Line chart

Line chart is the simple form of chart, which connects a series of data points with a straight line. Usually, it is used for trend analysis, forecasting, or visualizing large data points.

The following code snippet shows how to select a line chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ChartType="Line" 
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}"
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ChartType = PivotChartType.Line;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ChartType = PivotChartType.Line

{% endhighlight %}

{% endtabs %}

![line](Chart-Types_images/line.png)

### Spline chart

Spline chart is a simple form of chart, which connects the series of data points with an arc rather than a straight line.

The following code snippet shows how to select a spline chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ChartType="Spline" 
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}"
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ChartType = PivotChartType.Spline;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ChartType = PivotChartType.Spline

{% endhighlight %}

{% endtabs %}

![spline](Chart-Types_images/spline.png)

### Step line chart

Step line chart is another form of chart, which connects the series of data points by using horizontal and vertical lines.

The following code snippet shows how to select a step line chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ChartType="StepLine" 
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}"
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ChartType = PivotChartType.StepLine;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ChartType = PivotChartType.StepLine

{% endhighlight %}

{% endtabs %}

![stepLine](Chart-Types_images/stepLine.png)

## Scatter chart

Scatter chart is a collection of points that are plotted in the rectangular co-ordinate system. It is often used in relationship analysis up to one independent variable. The size of scatter segments can be modified with the help of `ScatterWidth` and `ScatterHeight` properties.

The following code snippet shows how to select a scatter chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ChartType="Scatter" ScatterWidth="20" ScatterHeight="20"
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}"
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ChartType = PivotChartType.Scatter;
PivotChart1.ScatterWidth = 20;
PivotChart1.ScatterHeight = 20;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ChartType = PivotChartType.Scatter
PivotChart1.ScatterWidth = 20
PivotChart1.ScatterHeight = 20

{% endhighlight %}

{% endtabs %}

![scatter_customScatterSize](Chart-Types_images/scatter_customScatterSize.png)

## Pie chart

Pie chart renders Y values as slices in a pie. These slices are rendered in a proportion to the whole which is simply the sum of all the Y values in the series. Pie chart can display only one data series at a time.

The following code snippet shows how to select a pie chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ChartType="Pie" 
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}"
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ChartType = PivotChartType.Pie;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ChartType = PivotChartType.Pie

{% endhighlight %}

{% endtabs %}

![pie](Chart-Types_images/pie.png)

N> Pie chart should not be used for comparison analysis of large data points, because it is harder for people to estimate angles rather than distance.

## Fast charts

### Fast bar bitmap chart

Fast bar bitmap charts are similar to bar type charts except that it boosts up the performance of loading large data points.

The following code snippet shows how to select a fast bar bitmap chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ChartType="FastBarBitmap" 
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}"
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ChartType = PivotChartType.FastBarBitmap;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ChartType = PivotChartType.FastBarBitmap

{% endhighlight %}

{% endtabs %}

![fastBarBitmap](Chart-Types_images/fastBarBitmap.png)

### Fast column bitmap chart

Fast column bitmap charts are similar to column type charts except that it boosts up the performance of loading large data points.

The following code snippet shows how to select a fast column bitmap chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ChartType="FastColumnBitmap"
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}"
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ChartType = PivotChartType.FastColumnBitmap;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ChartType = PivotChartType.FastColumnBitmap

{% endhighlight %}

{% endtabs %}

![fastColumnBitmap](Chart-Types_images/fastColumnBitmap.png)

### Fast line chart

The fast line chart is a special kind of line chart that renders a huge collection of data points using the polyline segment.

The following code snippet shows how to select a fast line chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ChartType="FastLine"
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}"
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ChartType = PivotChartType.FastLine;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ChartType = PivotChartType.FastLine

{% endhighlight %}

{% endtabs %}

![fastLine](Chart-Types_images/fastLine.png)

### Fast line bitmap chart

The fast line bitmap chart displays a series of line segments that are rendered by using the `WriteableBitmap`. The advantage of this chart is rendering a million data points in a fraction of seconds.

The following code snippet shows how to select a fast line bitmap chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ChartType="FastLineBitmap"
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}"
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ChartType = PivotChartType.FastLineBitmap;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ChartType = PivotChartType.FastLineBitmap

{% endhighlight %}

{% endtabs %}

![fastLineBitmap](Chart-Types_images/fastLineBitmap.png)

As this chart is rendered using bitmap, there might be some jagged lines at the edges and it can be reduced by enabling the `EnableAntiAliasing` property as follows.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ChartType="FastLineBitmap" EnableAntiAliasing="True"
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}" 
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ChartType = PivotChartType.FastLineBitmap;
PivotChart1.EnableAntiAliasing = true;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ChartType = PivotChartType.FastLineBitmap
PivotChart1.EnableAntiAliasing = True

{% endhighlight %}

{% endtabs %}

![fastLineBitmap_antiAlaisingEnabled](Chart-Types_images/fastLineBitmap_antiAlaisingEnabled.png)

### Fast scatter bitmap chart

The fast scatter bitmap chart is used to display a large set of scatter points. The following code snippet shows how to select a fast scatter bitmap chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ChartType="FastScatterBitmap" 
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}"
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ChartType = PivotChartType.FastScatterBitmap;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ChartType = PivotChartType.FastScatterBitmap

{% endhighlight %}

{% endtabs %}

![fastScatterBitmap](Chart-Types_images/fastScatterBitmap.png)

The size of the scatter points can be customized with the help of `ScatterWidth` and `ScatterHeight` properties as follows.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ChartType="FastScatterBitmap" ScatterWidth="7" ScatterHeight="7" 
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}" 
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ChartType = PivotChartType.FastScatterBitmap;
PivotChart1.ScatterWidth = 7;
PivotChart1.ScatterHeight = 7;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ChartType = PivotChartType.FastScatterBitmap
PivotChart1.ScatterWidth = 7
PivotChart1.ScatterHeight = 7

{% endhighlight %}

{% endtabs %}

![fastScatterBitmap_customScatterSize](Chart-Types_images/fastScatterBitmap_customScatterSize.png)

### Fast stacking column bitmap chart

The fast stacking column charts are similar to stacking column charts but it loads faster and provides better performance comparatively.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ChartType="FastStackingColumnBitmap"
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}" 
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ChartType = PivotChartType.FastStackingColumnBitmap;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ChartType = PivotChartType.FastStackingColumnBitmap

{% endhighlight %}

{% endtabs %}

![fastStackingColumnBitmap](Chart-Types_images/fastStackingColumnBitmap.png)

### Fast step line bitmap chart

The fast step line charts are the high performance version of step line charts.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ChartType="FastStepLineBitmap" 
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}" 
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ChartType = PivotChartType.FastStepLineBitmap;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ChartType = PivotChartType.FastStepLineBitmap

{% endhighlight %}

{% endtabs %}

![fastStepLineBitmap](Chart-Types_images/fastStepLineBitmap.png)

As fast step line bitmap chart is rendered using bitmap, some jagged lines can be occurred at the edges and it can be reduced by enabling the  `EnableAntiAliasing` property as follows.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ChartType="FastStepLineBitmap" EnableAntiAliasing="True" 
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}" 
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ChartType = PivotChartType.FastStepLineBitmap;
PivotChart1.EnableAntiAliasing = true;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ChartType = PivotChartType.FastStepLineBitmap
PivotChart1.EnableAntiAliasing = True

{% endhighlight %}

{% endtabs %}

![fastStepLineBitmap_antiAlaisingEnabled](Chart-Types_images/fastStepLineBitmap_antiAlaisingEnabled.png)

A demo sample is available in the following location.

{system drive}:\User3s\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\Samples\UWP\SampleBrowser\PivotChart\PivotChart\View\ChartType.xaml
