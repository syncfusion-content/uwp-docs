---
layout: post
title: Orientation | SfBulletGraph | uwp | Syncfusion
description: Orientation 
platform: uwp
control: SfBulletGraph
documentation: ug
---

# Orientation 

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
