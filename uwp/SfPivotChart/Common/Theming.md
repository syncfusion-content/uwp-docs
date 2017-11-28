---
layout: post
title: Theming | SfPivotChart | UWP | Syncfusion
description: Theming
platform: UWP
control: SfPivotChart
documentation: ug
---

# Theming

Theming is the process of applying particular settings to the visual elements of a control. Following in-built themes are supported in SfPivotChart control.

* Blend
* Lime
* Metro
* Office2010Black
* Office2010Blue
* Office2010Silver
* Office2013DarkGray
* Office2013LightGray
* Office2013White
* Office2016Colorful
* Office2016DarkGray
* Office2016White
* Office365
* Saffron
* VisualStudio2013
* VisualStudio2015

By using the property of `ChartVisualStyle` in SfPivotChart, you can set the visual style of the control. By default, the `Metro` theme is applied. The following code snippet shows how to change the visual style for SfPivotChart.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" ChartVisualStyle="Blend"
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}"
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}"/>

{% endhighlight %}

{% highlight c# %}

PivotChart1.ChartVisualStyle = ChartVisualStyle.Blend;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ChartVisualStyle = ChartVisualStyle.Blend

{% endhighlight %}

{% endtabs %}

![](Theming_images/blendTheme.png)