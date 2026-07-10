---
layout: post
title: Flow Direction in UWP Bullet Graph control | Syncfusion
description: Learn here all about Flow Direction support in Syncfusion UWP Bullet Graph (SfBulletGraph) control and more.
platform: uwp
control: SfBulletGraph
documentation: ug
---

# Flow Direction

By default the flow direction of SfBulletGraph is forward (LTR). It can be customized by using the **FlowDirection** property respectively.

>Note:- When the Orientation of **SfBulletGraph** is **Horizontal**, the default flow direction will be Left to Right. When the Orientation of **SfBulletGraph** is **Vertical**, the default flow direction will be Top to Bottom.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfBulletGraph FlowDirection="Forward" />

{% endhighlight %}

{% highlight c# %}

SfBulletGraph bullet = new SfBulletGraph();
bullet.FlowDirection = BulletGraphFlowDirection.Forward;
this.Grid.Children.Add(bullet);

{% endhighlight %}
{% endtabs %}

<table>
<tr>
<td>
{{'![Vertical Flow Direction Control](Flow-Direction_images/Flow-Direction_img1.jpeg)'| markdownify }}
</td>
<td>
{{'![Horizontal Flow Direction Control](Flow-Direction_images/Flow-Direction_img2.jpeg)'| markdownify }}
{{'____'| markdownify }}
</td></tr>
</table>