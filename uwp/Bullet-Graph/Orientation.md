---
layout: post
title: Orientation in UWP Bullet Graph control | Syncfusion
description: Learn here all about Orientation support in Syncfusion UWP Bullet Graph (SfBulletGraph) control and more.
platform: uwp
control: SfBulletGraph
documentation: ug
---

# Orientation in UWP Bullet Graph (SfBulletGraph)

By default orientation of SfBulletGraph is horizontal. It can be customized by using **Orientation** property respectively.

{% tabs %}
{% highlight xaml %}

    <syncfusion:SfBulletGraph Orientation="Vertical">
    </syncfusion:SfBulletGraph>

{% endhighlight %}

{% highlight c# %}

     SfBulletGraph bullet = new SfBulletGraph();
     bullet.Orientation = Orientation.Vertical;
     this.Grid.Children.Add(bullet);

{% endhighlight %}

{% endtabs %}
<table>
<tr>
<td>
{{'![](Orientation_images/Orientation_img1.jpeg)'| markdownify }}
</td><td>
{{'![](Orientation_images/Orientation_img2.jpeg)'| markdownify }}
</td></tr>
</table>
