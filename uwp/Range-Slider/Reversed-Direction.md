---
layout: post
title: Reversed Direction in UWP Range Slider control | Syncfusion
description: Learn here all about Reversed Direction support in Syncfusion UWP Range Slider (SfRangeSlider) control and more.
platform: uwp
control: SfRange Slider 
documentation: ug
---

# Reversed Direction in UWP Range Slider (SfRangeSlider)

The direction of increasing value can be changed using IsDirectionReversed property. If this property is set to True, the direction of increasing value is towards left in the horizontal orientation and down in the vertical orientation. The default is false. 


{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider x:Name="rangeSlider" Width="200" Minimum="0" Maximum="100" Value="10" IsDirectionReversed="True"  />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

   rangeSlider.IsDirectionReversed = true;

{% endhighlight %}

{% highlight VB %}

  rangeSlider.IsDirectionReversed = true

{% endhighlight %}

{% endtabs %}

![RangeSlider IsDirectionReversed view](Direction-Reversed_images/Direction-Reversed_img1.jpg)





