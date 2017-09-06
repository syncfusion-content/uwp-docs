---
layout: post
title: Quantitative Scale  | SfBulletGraph | uwp | Syncfusion
description: Quantitative Scale  
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

    SfBulletGraph bullet = new SfBulletGraph();
    bullet.QuantitativeScaleLength = 300;
    bullet.Minimum = 0;
    bullet.Maximum = 10;
    bullet.Interval = 2;
    this.Grid.Children.Add(bullet);

{% endhighlight %}
{% endtabs %}

![](Quantitative-scale_images/Quantitative-scale_img1.jpeg)
