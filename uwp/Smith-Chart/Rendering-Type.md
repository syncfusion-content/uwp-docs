---
layout: post
title: Rendering Type in UWP Smith Chart control | Syncfusion
description: Learn here all about Rendering Type support in Syncfusion UWP Smith Chart (SfSmithChart) control and more.
platform: uwp
control: SfSmithChart
documentation: ug
---

# Rendering Type in UWP Smith Chart (SfSmithChart)

SfSmithChart plots the transmission line in two different ways by using the [`RenderingType`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.SmithChart.SfSmithChart.html#Syncfusion_UI_Xaml_SmithChart_SfSmithChart_RenderingType) property. The two ways are given below.

## Impedance

In the impedance Smith chart, normalized resistance circles and normalized reactance curves are drawn from right to left. Axis label ranges start from left to right.

Impedance is the default rendering type of SmithChart.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfSmithChart RenderingType="Impedance" />

{% endhighlight %}

{% highlight C# %} 

SfSmithChart chart = new SfSmithChart();
chart.RenderingType = RenderingType.Impedance;

{% endhighlight %}
    
{% endtabs %}

![SmithChart Impedance Chart](Rendering-Type_images/Rendering-Type_img1.png)

## Admittance

In the Admittance Smith chart, normalized resistance circles and normalized reactance curves are drawn from left to right. Axis label ranges start from right to left.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfSmithChart RenderingType="Admittance" />

{% endhighlight %}

{% highlight C# %} 

SfSmithChart chart = new SfSmithChart();
chart.RenderingType = RenderingType.Admittance;

{% endhighlight %}
    
{% endtabs %}

![SmithChart Admittance Chart](Rendering-Type_images/Rendering-Type_img2.png)
