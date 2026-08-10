---
layout: post
title: Tooltip in UWP Pivot Chart | Syncfusion®
description: Tooltip in the UWP Pivot Chart displays detailed information about data points and supports customization of content and appearance.
platform: uwp
control: SfPivotChart
documentation: ug
---

# Tooltip in UWP Pivot Chart

The SfPivotChart provides tooltip support by which the series information such as measure, x-axis values, y-axis values, and series name can be displayed over the chart area, when the mouse pointer is moved over chart points.

The following code snippet shows how to enable the series tooltip by using [`ShowToolTip`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.PivotChart.SfPivotChart.html#Syncfusion_UI_Xaml_PivotChart_SfPivotChart_ShowToolTip) property.

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

![enableRelationalTooltip](Tooltip_images/enableRelationalTooltip.png)
