---
layout: post
title: Theming in UWP Pivot Chart control | Syncfusion
description: Learn here all about Theming support in Syncfusion UWP Pivot Chart (SfPivotChart) control and more.
platform: UWP
control: SfPivotChart
documentation: ug
---

# Theming in UWP Pivot Chart (SfPivotChart)

Theming is the process of applying particular settings to visual elements of the control. Following built-in themes are supported in the SfPivotChart control.

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

By using the `ChartVisualStyle` property in the SfPivotChart, you can set the visual style of a control. By default, the `Metro` theme is applied. The following code snippet shows how to change the visual style for the SfPivotChart.

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

![blendTheme](Theming_images/blendTheme.png)
