---
layout: post
title: Ticks in UWP Bullet Graph control | Syncfusion
description: Learn here all about Ticks support in Syncfusion UWP Bullet Graph (SfBulletGraph) control and more.
platform: uwp
control: SfBulletGraph
documentation: ug
---

# Ticks in UWP Bullet Graph (SfBulletGraph)

Quantitative scale is displayed with two types of ticks: 

* Major ticks, the primary scale indicators.
* Minor ticks, the secondary scale indicators that fall in between the major ticks.

## Customizing Ticks

The Interval property is used to calculate the Major tick count for a SfBulletGraph. Like ticks, small ticks are calculated using the MinorTicksPerInterval property.

The stroke of the major and minor ticks is customized by setting the **MajorTickStroke** and **MinorTickStroke** properties. The size can be modified by using the **MajorTickSize** and **MinorTickSize** properties. By setting **MajorTickStrokeThickness** and **MinorTickStrokeThickness**, the stroke’s thickness can be customized.

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfBulletGraph   Interval="2"
                                MinorTicksPerInterval="3"
                                MajorTickSize="15"
                                MinorTickSize="10"
                                MajorTickStroke="Red"      
                                MinorTickStroke="Green">            
        </syncfusion:SfBulletGraph>

{% endhighlight %}

{% highlight c# %}

      SfBulletGraph bullet = new SfBulletGraph();
      bullet.MinorTicksPerInterval = 3;
      bullet.MajorTickSize = 15;
      bullet.MinorTickSize = 10;
      bullet.MajorTickStroke = new SolidColorBrush(Colors.Red);
      bullet.MinorTickStroke = new SolidColorBrush(Colors.Green);
      this.Grid.Children.Add(bullet);

{% endhighlight %}
{% endtabs %}

![Ticks_img](Ticks_images/Ticks_img.jpg)

## TickPosition

The ticks in the scale can be placed above or below the ranges of the quantitative scale by choosing the options available in the **TickPosition** property. 

They are:

1. Below (Default)
2. Above
3. Cross

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfBulletGraph   TickPosition="Cross">
    </syncfusion:SfBulletGraph>

{% endhighlight %}

{% highlight c# %}

    SfBulletGraph bullet = new SfBulletGraph();
    bullet.TickPosition = BulletGraphTicksPosition.Cross; 
    this.Grid.Children.Add(bullet);

{% endhighlight %}
{% endtabs %}

![Ticks_img1](Ticks_images/Ticks_img1.jpeg)
