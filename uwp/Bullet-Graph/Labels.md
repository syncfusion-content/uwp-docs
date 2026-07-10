---
layout: post
title: Labels in UWP Bullet Graph control | Syncfusion
description: Learn here all about Labels support in Syncfusion UWP Bullet Graph (SfBulletGraph) control and more.
platform: uwp
control: SfBulletGraph
documentation: ug
---

# Labels in UWP Bullet Graph (SfBulletGraph)

A quantitative scale label specifies the numeric value according to the major ticks in the range of the scale.

## Customizing labels

The labels can be positioned far away from the Quantitative scale by using the **LabelOffset** property and the default value of this **LabelOffset** property value is 0. The foreground of the label is customized by setting **LabelStroke**. By setting **LabelSize**, the font size of the labels is modified. The label content can be formatted by using the **LabelFormat** property.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfBulletGraph LabelSize="20"
                          LabelOffset="5" 
                          LabelStroke="Red"
                          LabelFormat="" />

{% endhighlight %}

{% highlight c# %}

SfBulletGraph bullet = new SfBulletGraph();
bullet.LabelOffset = 5;
bullet.LabelSize = 20;
bullet.LabelFormat = "";
bullet.LabelStroke = new SolidColorBrush(Colors.Red);
this.Grid.Children.Add(bullet);

{% endhighlight %}
{% endtabs %}

![Labels_img1](Labels_images/Labels_img1.jpg)

## Label position

The labels in the scale can be placed above or below the qualitative ranges by choosing the following options available in the **LabelPosition** property. 

1. Below (Default)
2. Above

{% tabs %}
{% highlight xaml %}

<syncfusion:SfBulletGraph LabelPosition="Above" />

{% endhighlight %}

{% highlight c# %}

SfBulletGraph bullet = new SfBulletGraph();
bullet.LabelPosition = BulletGraphLabelsPosition.Above;
this.Grid.Children.Add(bullet);

{% endhighlight %}
{% endtabs %}

![Labels_img2](Labels_images/Labels_img2.jpg)
