---
layout: post
title: Sorting | SfChart | uwp | Syncfusion
description: sorting 
platform: uwp
control: SfChart
documentation: ug
---

# Sorting

Chart provides the support for sorting the data point rendering either in ascending or descending based on X or Y axis.

### Enable Sorting
Ths `IsSortData` property used to enable the sorting in series.

### Changing sorting direction

The `SortDirection` property defines the direction of sorting either in Ascending or Descending based on x or y value.

### Changing sorting axis

This `SortBy` property decides whether sorting should be done based on x or y values.


The following example illustrates a simple chart (without apply sorting):

![](sorting_chart_images/sorting_1.png)


## Sorting for category(non-linear) axis

**Sorting x axis in ascending order**:

{% highlight xml %}
<syncfusion:ColumnSeries IsSortData="True" SortBy="X"  
	
	                     SortDirection="Ascending"

                         ItemsSource="{Binding Demands}" Interior="#4A4A4A"

                         XBindingPath="Demand"  YBindingPath="Year2011"/>

{% endhighlight %}

![](sorting_chart_images/sorting_2.png)


**Sorting x axis in descending order**:

{% highlight xml %}

<syncfusion:ColumnSeries IsSortData="True" SortBy="X"  
	 
	                     SortDirection="Descending"

                         ItemsSource="{Binding Demands}" Interior="#4A4A4A"

                         XBindingPath="Demand"  YBindingPath="Year2011"/>

{% endhighlight %}

![](sorting_chart_images/sorting_3.png)


**Sorting y axis in ascending order**:

{% highlight xml %}

<syncfusion:ColumnSeries IsSortData="True" SortBy="Y" 
	                   
					     SortDirection="Ascending"

                         ItemsSource="{Binding Demands}" Interior="#4A4A4A"

                         XBindingPath="Demand"  YBindingPath="Year2011"/>


{% endhighlight %}

![](sorting_chart_images/sorting_4.png)


**Sorting y axis in descending order**:

{% highlight xml %}

<syncfusion:ColumnSeries IsSortData="True" SortBy="Y"  
	
	                     SortDirection="Descending"

                         ItemsSource="{Binding Demands}" Interior="#4A4A4A"

                         XBindingPath="Demand"  YBindingPath="Year2011"/>


{% endhighlight %}

![](sorting_chart_images/sorting_5.png)

N> This feature is primarily applicable for indexed (non-linear) axis like CategoryAxis. For linear axis like NumericalAxis, only the order of rendering will be sorted. i.e., the order in which the data point is being rendered.


## Sorting for linear axis

As mentioned above, the sorting for the linear axis is different from CategoryAxis. Here the rendering order of the data point (x or y) will be sorted.

This will be useful especially when we have one or more values added in same data point. Also this rendering order sorting will be captured by applying Palette to each point.

The following example illustrates a simple chart having AutumnBrights palette (without apply sorting):

![](sorting_chart_images/linearaxis_nosort.png)

**Sorting x axis in ascending order**

{% highlight xml %}

<syncfusion:ColumnSeries IsSortData="True" SortBy="X" Palette="AutumnBrights"

                         SortDirection="Ascending"

                         ItemsSource="{Binding Demands}" 

                         XBindingPath="Position"  YBindingPath="Year2011"/>

{% endhighlight %}

![](sorting_chart_images/linearaxis_sort1.png)

**Sorting x axis in descending order**

{% highlight xml %}

<syncfusion:ColumnSeries IsSortData="True" SortBy="X" 
	
	                     Palette="AutumnBrights"

                         SortDirection="Descending"

                         ItemsSource="{Binding Demands}" 

                         XBindingPath="Position"  YBindingPath="Year2011"/>

{% endhighlight %}

![](sorting_chart_images/linearaxis_sort2.png)

**Sorting y axis in ascending order**

{% highlight xml %}
<syncfusion:ColumnSeries IsSortData="True" SortBy="Y" 
	
	                     Palette="AutumnBrights"

                         SortDirection="Ascending"

                         ItemsSource="{Binding Demands}" 

                         XBindingPath="Position"  YBindingPath="Year2011"/>

{% endhighlight %}

![](sorting_chart_images/linearaxis_sort3.png)

**Sorting y axis in descending order**

{% highlight xml %}
<syncfusion:ColumnSeries IsSortData="True" SortBy="Y" 
	
	                     Palette="AutumnBrights"

                         SortDirection="Descending"

                         ItemsSource="{Binding Demands}" 

                         XBindingPath="Position"  YBindingPath="Year2011"/>

{% endhighlight %}

![](sorting_chart_images/linearaxis_sort4.png)


