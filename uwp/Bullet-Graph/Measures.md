---
layout: post
title: Measures in UWP Bullet Graph control | Syncfusion
description: Learn here all about Measures support in Syncfusion UWP Bullet Graph (SfBulletGraph) control and more.
platform: uwp
control: SfBulletGraph
documentation: ug
---

# Measures in UWP Bullet Graph (SfBulletGraph)

## Featured Measure

Featured measure is used to display the primary data, or the current value of the data that you are measuring. It should usually be encoded as a bar.

**Customizing Featured Measure**

The value of the featured measure of the bullet graph is set by the **FeaturedMeasure** property. By setting the **FeaturedMeasureBarStroke** property, the stroke of the feature measure bar can be customized. The thickness of the featured measure bar is modified by using **FeaturedMeasureBarStrokeThickness**. 

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfBulletGraph FeaturedMeasure="5" FeaturedMeasureBarStroke="Red"
    FeaturedMeasureBarStrokeThickness="10">                             
    </syncfusion:SfBulletGraph>

{% endhighlight %}

{% highlight c# %}
 
    SfBulletGraph bullet = new SfBulletGraph();
    bullet.FeaturedMeasure = 5;
    bullet.FeaturedMeasureBarStroke = new SolidColorBrush(Colors.Black);
    bullet.FeaturedMeasureBarStrokeThickness = 10;
    this.Grid.Children.Add(bullet);

{% endhighlight %}
{% endtabs %}

![Measures_img1](Measures_images/Measures_img1.jpeg)

## Comparative Measure

Comparative measure should be less visually dominant than the featured measure. It should always be encoded as a short line that runs perpendicular to the orientation of the graph. A good example would be a target for YTD revenue. Whenever the featured measure intersects a comparative measure, the comparative measure should appear behind the featured measure.

**Customizing Comparative Measure**

The value of the comparative measure is set by using the **ComparativeMeasure** property. By setting the **ComparativeMeasureSymbolStroke** property, the stroke of the comparative measure symbol is customized. The thickness of the comparative measure symbol is modified by using **ComparativeMeasureSymbolStrokeThickness**. 

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfBulletGraph ComparativeMeasure="7"
    ComparativeMeasureSymbolStroke="Red"
    ComparativeMeasureSymbolStrokeThickness="6">
    </syncfusion:SfBulletGraph>

{% endhighlight %}

{% highlight c# %}

    SfBulletGraph bullet = new SfBulletGraph();
    bullet.ComparativeMeasure = 7;
    bullet.ComparativeMeasureSymbolStroke = new SolidColorBrush(Colors.Black);
    bullet.ComparativeMeasureSymbolStrokeThickness = 10;
    this.Grid.Children.Add(bullet);

{% endhighlight %}
{% endtabs %}

![Measures_img2](Measures_images/Measures_img2.jpg)
