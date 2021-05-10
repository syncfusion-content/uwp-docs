---
layout: post
title: Ticks in UWP Radial Slider control | Syncfusion
description: Learn here all about Ticks support in Syncfusion UWP Radial Slider (SfRadialSlider) control and more.
platform: uwp
control: SfRadial Slider 
documentation: ug
---

# Ticks in UWP Radial Slider (SfRadialSlider)

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


![Concepts--and-Features_img2](Concepts--and-Features_images/Concepts--and-Features_img2.png)

## Displaying Maximum Value

Maximum Value of SfRadialSlider can be displayed even the difference between Maximum and Minimum value of SfRadialSlider is not divisible by TickFrequency. This behavior can be enabled by setting the ShowMaximumValue property of SfRadialSlider to true.

{% tabs %}

{% highlight xaml %}

<navigation:SfRadialSlider x:Name="sfradialslider" Maximum="100" 
                                   TickFrequency="12" ShowMaximumValue="true"/>

{% endhighlight %}


{% highlight C# %}

SfRadialSlider radialSlider = new SfRadialSlider() { Maximum = 100, TickFrequency = 12, ShowMaximumValue = true };

{% endhighlight %}

{% highlight VB %}

Dim radialSlider As New SfRadialSlider() With { _
	Key .Maximum = 100, _
	Key .TickFrequency = 12, _
	Key .ShowMaximumValue = True _
}

{% endhighlight %}

{% endtabs %}


![Concepts--and-Features_img18](Concepts--and-Features_images/Concepts--and-Features_img18.png)
