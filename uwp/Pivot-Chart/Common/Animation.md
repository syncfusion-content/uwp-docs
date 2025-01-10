---
layout: post
title: Animation in UWP Pivot Chart control | Syncfusion
description: Learn here all about Animation support in Syncfusion® UWP Pivot Chart (SfPivotChart) control and more.
platform: uwp
control: SfPivotChart
documentation: ug
---

# Animation in UWP Pivot Chart (SfPivotChart)

The SfPivotChart allows you to animate the chart series when loading and changing the data source. An animation in the chart can be enabled by setting the `EnableAnimation` property to true and defining the corresponding animation speed with the `AnimationDuration` property.

The following chart types support animation:

* Column
* Stacking column
* Stacking column 100
* Bar
* Stacking bar
* Line
* Spline
* Area
* Stacking area
* Spline area
* Scatter
* Pie

You can use the following snippet to enable animation in the SfPivotChart.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" EnableAnimation="True" AnimationDuration="0:0:3"
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}" PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}"/>

{% endhighlight %}

{% highlight c# %}

PivotChart1.EnableAnimation = true;
PivotChart1.AnimationDuration = new TimeSpan(0, 0, 3);

{% endhighlight %}

{% highlight vb %}

PivotChart1.EnableAnimation = True
PivotChart1.AnimationDuration = New TimeSpan(0, 0, 3)

{% endhighlight %}

{% endtabs %}
