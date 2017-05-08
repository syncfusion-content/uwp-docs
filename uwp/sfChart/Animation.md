---
layout: post
title: Animation | SfChart | uwp | Syncfusion
description: animation
platform: uwp
control: SfChart
documentation: ug
---

# Animation

SfChartAnimation allows you to animate the chart series on loading, and whenever the ItemsSource changes. Animation in chart can be enabled by setting the EnableAnimation property as True and defining the corresponding animation speed with AnimationDuration property.

The following types of series support Animation.

* Line
* Column
* Bar
* Area
* Scatter
* Bubble
* Spline
* Spline area
* Stacking column
* Stacking bar
* Stacking area
* Pie



The following APIs are used to customize the Animation.

Customization API for Animation

<table>
<tr>
<th>
Property</th><th>
Definition</th></th>
<tr>
<td>
EnableAnimation</td><td>
Gets or sets the bool value that represents a value to enable the animation for series.</td></tr>
<tr>
<td>
AnimationDuration</td><td>
Gets or sets the TimeSpan value that represents the animation speed for the chart.</td></tr>
</table>


The following example shows the Animation feature for chart series.

{% tabs %}

{% highlight xaml %}


<syncfusion:SfChart>

    <syncfusion:ColumnSeries EnableAnimation="True" 

                             AnimationDuration="00:00:02" 

                             Palette="Metro" 

                             XBindingPath="Category" 

                             YBindingPath="Count"

                             ItemsSource="{Binding Data}"/>

 </syncfusion:SfChart>


{% endhighlight %}

{% highlight c# %}

ColumnSeries columnSeries = new ColumnSeries()
{

        ItemsSource = new ViewModel().Data,

        XBindingPath = "Category",

        YBindingPath = "Count",

        Palette = ChartColorPalette.Metro,

        EnableAnimation = true,

        AnimationDuration = new TimeSpan(00, 00, 02)

};

chart.Series.Add(columnSeries);

{% endhighlight %}

{% endtabs %}
