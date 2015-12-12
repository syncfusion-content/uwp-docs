---
layout: post
title: Quantitative scale  | SfBulletGraph | uwp | Syncfusion
description: Quantitative scale  
platform: uwp
control: SfBulletGraph
documentation: ug
---

# Quantitative Scale 

Quantitative scale contains two major components such as ticks and labels which gives the looks of bar graph. It defines the frequency of labels and tick marks with overall Minimum and Maximum values for declared Interval. The length of the quantitative scale can be customized by using the **QuantitativeScaleLength** property.

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfBulletGraph QuantitativeScaleLength="300" Minimum="0" Maximum="10"  Interval="2"/>

{% endhighlight %}

{% highlight c# %}

    SfBulletGraph bulletgraph = new SfBulletGraph();
    bulletgraph.QuantitativeScaleLength = 300;
    bulletgraph.Minimum = 0;
    bulletgraph.Maximum = 10;
    bulletgraph.Interval = 2;
    this.Grid.Children.Add(bulletgraph);

{% endhighlight %}
{% endtabs %}

![](Quantitative-scale_images/Quantitative-scale_img1.jpeg)
