---
layout: post
title: Gauge Type | SfCircularGauge | uwp | Syncfusion
description: Gauge Type
platform: uwp
control: SfCircularGauge
documentation: ug
---

# Gauge Type

SfCircularGauge type is determined by positioning the control towards particular direction.
GaugeType is an enum property that provides the option to select type of the SfCircularGauge type, which contains following options.

* Default,
* East,
* West,
* North,
* South,
* NorthEast,
* NorthWest,
* SouthEast,
* SouthWest 

{% tabs %}
{% highlight xml %}

    <syncfusion:SfCircularGauge GaugeType="East"/>

{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circularGauge = new SfCircularGauge();
    circularGauge.GaugeType = CircularGaugeTypes.East;
    this.Grid.Children.Add(circularGauge);
    
{% endhighlight %}
{% endtabs %}

<table>
<tr>
<td>
{{'![](tab_images/tab_img1.jpeg)'| markdownify }}
</td></tr>
</table>

<table>
<tr>
<td>
{{'![](tab_images/tab_img2.jpeg)'| markdownify }}
</td><td>
{{'![](tab_images/tab_img3.jpeg)'| markdownify }}
</td></tr>
</table>

<table>
<tr>
<td>
{{'![](tab_images/tab_img4.jpeg)'| markdownify }}
</td><td>
{{'![](tab_images/tab_img5.jpeg)'| markdownify }}
</td></tr>
</table>

<table>
<tr>
<td>
{{'![](tab_images/tab_img6.jpeg)'| markdownify }}
</td><td>
{{'![](tab_images/tab_img7.jpeg)'| markdownify }}
</td></tr>
</table>

<table>
<tr>
<td>
{{'![](tab_images/tab_img8.jpeg)'| markdownify }}
</td><td>
{{'![](tab_images/tab_img9.jpeg)'| markdownify }}
</td></tr>
</table>
