---
layout: post
title: Tooltip in UWP Pivot Gauge | Syncfusion®
description: Tooltip in the UWP Pivot Gauge displays detailed information about gauge values and supports interactive data analysis and visualization.
platform: uwp
control: SfPivotGauge
documentation: ug
---

# Tooltip in UWP Pivot Gauge

The [SfPivotGauge](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.PivotGauge.SfPivotGauge.html) provides the information about values when the mouse pointer is moved over the gauge. The following code snippet illustrates how to show a tooltip by using the [ShowGaugeTooltip](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.PivotGauge.SfPivotGauge.html#Syncfusion_UI_Xaml_PivotGauge_SfPivotGauge_ShowGaugeTooltip) property.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGauge x:Name="PivotGauge1" ShowGaugeTooltip="True"
                         ItemSource="{Binding ProductSalesData}" PivotRows="{Binding PivotRows}"
                         PivotColumns="{Binding PivotColumns}" PivotCalculations="{Binding PivotCalculations}"/>

{% endhighlight %}

{% highlight c# %}

PivotGauge1.ShowGaugeTooltip = true;

{% endhighlight %}

{% highlight vb %}

PivotGauge1.ShowGaugeTooltip = True

{% endhighlight %}

{% endtabs %}

![UWP Pivot Gauge Tooltip](Tooltip_images/Tooltip.png)
