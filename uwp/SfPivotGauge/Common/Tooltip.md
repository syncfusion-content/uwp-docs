---
layout: post
title: Tooltip | SfPivotGauge | UWP | Syncfusion
description: Tooltip
platform: UWP
control: SfPivotGauge
documentation: ug
---

# Tooltip

SfPivotGauge provides the information about values when the mouse pointer is moved over the gauge. The below code snippet illustrates how to show tooltip by using `ShowGaugeTooltip` property.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGauge x:Name="PivotGauge1" ShowGaugeTooltip="True"
                         ItemSource="{Binding ProductSalesData}" PivotRows="{Binding PivotRows}"
                         PivotColumns="{Binding PivotColumns}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotGauge>

{% endhighlight %}

{% highlight c# %}

PivotGauge1.ShowGaugeTooltip = true;

{% endhighlight %}

{% highlight vb %}

PivotGauge1.ShowGaugeTooltip = True

{% endhighlight %}

{% endtabs %}

![](Tooltip_images/Tooltip.png)