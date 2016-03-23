---
layout: post
title: Dealing with Ticks of SfRadialSlider control for UWP
description: Dealing with Ticks of SfRadialSlider control for UWP 
platform: uwp
control: SfRadial Slider 
documentation: ug
---

# Ticks 

Ticks are placed along the round track in a uniform manner. The position of tick marks can be customized.

## Tick Frequency

The Tick Frequency property is used to define the number of ticks along the track, based on Minimum and Maximum values.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfRadialSlider Minimum="0" Maximum="100"  x:Name="radialSlider"

TickFrequency="5" />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

radialSlider.TickFrequency = 5;

{% endhighlight %}

{% highlight VB %}

radialSlider.TickFrequency = 5

{% endhighlight %}

{% endtabs %}


![](Concepts--and-Features_images/Concepts--and-Features_img2.png)
