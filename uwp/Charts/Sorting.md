---
layout: post
title: Sorting in UWP Charts control | Syncfusion
description: Learn here about how to add proper Sorting data points support in Syncfusion UWP Charts (SfChart) control and more.
platform: uwp
control: SfChart
documentation: ug
---

# Sorting in UWP Charts (SfChart)

Chart provides the support for sorting the data point rendering either in ascending or descending based on X or Y axis.

### Enable Sorting
This [`IsSortData`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_IsSortData) property used to enable the sorting in series.

### Changing sorting direction

The [`SortDirection`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_SortDirection) property defines the direction of sorting either in Ascending or Descending based on x or y value.

### Changing sorting axis

This [`SortBy`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_SortBy) property decides whether sorting should be done based on [`X`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SortingAxis.html#Syncfusion_UI_Xaml_Charts_SortingAxis_X) or [`Y`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.SortingAxis.html#Syncfusion_UI_Xaml_Charts_SortingAxis_Y) values.


The following example illustrates a simple chart (without apply sorting):

![Axis without sorting in UWP Chart](sorting_chart_images/sorting_1.png)


## Sorting for category(non-linear) axis

**Sorting x axis in ascending order**:

{% tabs %}

{% highlight xml %}
<syncfusion:ColumnSeries IsSortData="True" SortBy="X"  
	
	                     SortDirection="Ascending"

                         ItemsSource="{Binding Demands}" Interior="#4A4A4A"

                         XBindingPath="Demand"  YBindingPath="Year2011"/>

{% endhighlight %}

{% highlight c# %}

ColumnSeries columnSeries = new ColumnSeries()
{

    IsSortData = true,

    SortBy = SortingAxis.X,

    SortDirection = Direction.Ascending,

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2011",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

chart.Series.Add(columnSeries);

{% endhighlight %}

{% endtabs %}

![Axis with sorting in UWP Chart](sorting_chart_images/sorting_2.png)


**Sorting x-axis in descending order**:

{% tabs %}

{% highlight xml %}

<syncfusion:ColumnSeries IsSortData="True" SortBy="X"  
	 
	                     SortDirection="Descending"

                         ItemsSource="{Binding Demands}" Interior="#4A4A4A"

                         XBindingPath="Demand"  YBindingPath="Year2011"/>

{% endhighlight %}

{% highlight c# %}

ColumnSeries columnSeries = new ColumnSeries()
{

    IsSortData = true,

    SortBy = SortingAxis.X,

    SortDirection = Direction.Descending,

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2011",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

chart.Series.Add(columnSeries);

{% endhighlight %}

{% endtabs %}

![Sorting x-axis in descending order in UWP Chart](sorting_chart_images/sorting_3.png)


**Sorting y axis in ascending order**:

{% tabs %}

{% highlight xml %}

<syncfusion:ColumnSeries IsSortData="True" SortBy="Y" 
	                   
					     SortDirection="Ascending"

                         ItemsSource="{Binding Demands}" Interior="#4A4A4A"

                         XBindingPath="Demand"  YBindingPath="Year2011"/>


{% endhighlight %}

{% highlight c# %}

ColumnSeries columnSeries = new ColumnSeries()
{

    IsSortData = true,

    SortBy = SortingAxis.Y,

    SortDirection = Direction.Ascending,

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2011",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

chart.Series.Add(columnSeries);

{% endhighlight %}

{% endtabs %}

![Sorting y-axis in ascending order in UWP Chart](sorting_chart_images/sorting_4.png)


**Sorting y axis in descending order**:

{% tabs %}

{% highlight xml %}

<syncfusion:ColumnSeries IsSortData="True" SortBy="Y"  
	
	                     SortDirection="Descending"

                         ItemsSource="{Binding Demands}" Interior="#4A4A4A"

                         XBindingPath="Demand"  YBindingPath="Year2011"/>


{% endhighlight %}

{% highlight c# %}

ColumnSeries columnSeries = new ColumnSeries()
{

    IsSortData = true,

    SortBy = SortingAxis.Y,

    SortDirection = Direction.Descending,

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Demand",

    YBindingPath = "Year2011",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

chart.Series.Add(columnSeries);

{% endhighlight %}

{% endtabs %}

![Sorting y-axis in descending order in UWP Chart](sorting_chart_images/sorting_5.png)

N> This feature is primarily applicable for indexed (non-linear) axis like [`CategoryAxis`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.CategoryAxis.html). For linear axis like [`NumericalAxis`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.NumericalAxis.html), only the order of rendering will be sorted. i.e., the order in which the data point is being rendered.


## Sorting for linear axis

As mentioned above, the sorting for the linear axis is different from [`CategoryAxis`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.CategoryAxis.html). Here the rendering order of the data point (x or y) will be sorted.

This will be useful especially when we have one or more values added in same data point. Also this rendering order sorting will be captured by applying [`Palette`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_Palette) to each point.

The following example illustrates a simple chart having [`AutumnBrights`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartColorPalette.html#Syncfusion_UI_Xaml_Charts_ChartColorPalette_AutumnBrights) palette (without apply sorting):

![Axis with sorting in UWP Chart](sorting_chart_images/linearaxis_nosort.png)

**Sorting x axis in ascending order**

{% tabs %}

{% highlight xml %}

<syncfusion:ColumnSeries IsSortData="True" SortBy="X" Palette="AutumnBrights"

                         SortDirection="Ascending"

                         ItemsSource="{Binding Demands}" 

                         XBindingPath="Position"  YBindingPath="Year2011"/>

{% endhighlight %}

{% highlight c# %}

ColumnSeries columnSeries = new ColumnSeries()
{

    IsSortData = true,

    SortBy = SortingAxis.X,

    SortDirection = Direction.Ascending,

    Palette = ChartColorPalette.AutumnBrights,

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Position",

    YBindingPath = "Year2011",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

chart.Series.Add(columnSeries);

{% endhighlight %}

{% endtabs %}

![Sorting x-axis in ascending order in UWP Chart](sorting_chart_images/linearaxis_sort1.png)

**Sorting x axis in descending order**

{% tabs %}

{% highlight xml %}

<syncfusion:ColumnSeries IsSortData="True" SortBy="X" 
	
	                     Palette="AutumnBrights"

                         SortDirection="Descending"

                         ItemsSource="{Binding Demands}" 

                         XBindingPath="Position"  YBindingPath="Year2011"/>

{% endhighlight %}

{% highlight c# %}

ColumnSeries columnSeries = new ColumnSeries()
{

    IsSortData = true,

    SortBy = SortingAxis.X,

    SortDirection = Direction.Descending,

    Palette = ChartColorPalette.AutumnBrights,

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Position",

    YBindingPath = "Year2011",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

chart.Series.Add(columnSeries);

{% endhighlight %}

{% endtabs %}

![Sorting x-axis in descending order in UWP Chart](sorting_chart_images/linearaxis_sort2.png)

**Sorting y axis in ascending order**

{% tabs %}

{% highlight xml %}
<syncfusion:ColumnSeries IsSortData="True" SortBy="Y" 
	
	                     Palette="AutumnBrights"

                         SortDirection="Ascending"

                         ItemsSource="{Binding Demands}" 

                         XBindingPath="Position"  YBindingPath="Year2011"/>

{% endhighlight %}

{% highlight c# %}

ColumnSeries columnSeries = new ColumnSeries()
{

    IsSortData = true,

    SortBy = SortingAxis.Y,

    SortDirection = Direction.Ascending,

    Palette = ChartColorPalette.AutumnBrights,

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Position",

    YBindingPath = "Year2011",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

chart.Series.Add(columnSeries);

{% endhighlight %}

{% endtabs %}

![Sorting y axis in ascending order in UWP Chart](sorting_chart_images/linearaxis_sort3.png)

**Sorting y axis in descending order**

{% tabs %}

{% highlight xml %}
<syncfusion:ColumnSeries IsSortData="True" SortBy="Y" 
	
	                     Palette="AutumnBrights"

                         SortDirection="Descending"

                         ItemsSource="{Binding Demands}" 

                         XBindingPath="Position"  YBindingPath="Year2011"/>

{% endhighlight %}

{% highlight c# %}

ColumnSeries columnSeries = new ColumnSeries()
{

    IsSortData = true,

    SortBy = SortingAxis.Y,

    SortDirection = Direction.Descending,

    Palette = ChartColorPalette.AutumnBrights,

    ItemsSource = new ViewModel().Demands,

    XBindingPath = "Position",

    YBindingPath = "Year2011",

    Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))

};

chart.Series.Add(columnSeries);

{% endhighlight %}

{% endtabs %}

![Sorting y-axis in descending order in UWP Chart](sorting_chart_images/linearaxis_sort4.png)


