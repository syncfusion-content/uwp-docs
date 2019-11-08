---
layout: post
title: Tooltip | SfPivotChart | UWP | Syncfusion
description: Tooltip
platform: UWP
control: SfPivotChart
documentation: ug
---

# Tooltip

The SfPivotChart provides tooltip support by which the series information such as measure, x-axis values, y-axis values, and series name can be displayed over the chart area, when the mouse pointer is moved over chart points.

The following code snippet shows how to enable the series tooltip by using `ShowToolTip` property.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ShowToolTip="True"
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}"
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ShowToolTip = true;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ShowToolTip = True

{% endhighlight %}

{% endtabs %}

![](Tooltip_images/enableRelationalTooltip.png)