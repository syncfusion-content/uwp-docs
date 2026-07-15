---
layout: post
title: Quantitative Scale in UWP Bullet Graph control | Syncfusion
description: Learn here all about Quantitative Scale support in Syncfusion UWP Bullet Graph (SfBulletGraph) control and more.
platform: uwp
control: SfBulletGraph
documentation: ug
---

# Quantitative Scale in UWP Bullet Graph (SfBulletGraph)

Quantitative scale contains two major components such as ticks and labels, which give the look of a bar graph. It defines the frequency of labels and tick marks with overall Minimum and Maximum values for the declared Interval. The length of the quantitative scale can be customized by using the [`QuantitativeScaleLength`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.BulletGraph.SfBulletGraph.html#Syncfusion_UI_Xaml_BulletGraph_SfBulletGraph_QuantitativeScaleLength) property.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfBulletGraph QuantitativeScaleLength="300" Minimum="0" Maximum="10"  Interval="2" />

{% endhighlight %}

{% highlight c# %}

SfBulletGraph bullet = new SfBulletGraph();
bullet.QuantitativeScaleLength = 300;
bullet.Minimum = 0;
bullet.Maximum = 10;
bullet.Interval = 2;
this.Grid.Children.Add(bullet);

{% endhighlight %}
{% endtabs %}

![Quantitative-scale_img1](Quantitative-scale_images/Quantitative-scale_img1.jpeg)
