---
layout: post
title: Setting Range in UWP Range Slider control | Syncfusion
description: Learn here all about Setting Range support in Syncfusion UWP Range Slider (SfRangeSlider) control and more.
platform: uwp
control: SfRange Slider 
documentation: ug
---

# Setting Range in UWP Range Slider (SfRangeSlider)

The SfRangeSlider control supports to select range of value using two Thumbs.  

## ShowRange  

When ShowRange property is set to true, two Thumbs are placed in the track. One Thumb is used to update the start of the range selection and another thumb is used to update the end of the range selection.  

{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider x:Name="rangeSlider" Width="200" VerticalAlignment="Center" Minimum="0" Maximum="100" ShowRange="True" RangeStart="40" RangeEnd="70"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

   rangeSlider.ShowRange = true;

{% endhighlight %}

{% highlight VB %}

   rangeSlider.ShowRange = True

{% endhighlight %}

{% endtabs %}

![RangeSlider ShowRange view](Range_images/Range_img1.jpg)

## RangeStart  

Gets or sets the start value of the range start.  

{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider x:Name="rangeSlider" Width="200" VerticalAlignment="Center" Minimum="0" Maximum="100" ShowRange="True" RangeStart="10" RangeEnd="70"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

   rangeSlider.RangeStart = 10;

{% endhighlight %}

{% highlight VB %}

  rangeSlider.RangeStart = 10

{% endhighlight %}

{% endtabs %}

![RangeSlider RangeStart view](Range_images/Range_img2.jpg)

## RangeEnd 

Gets or sets the end value of the range end.  

{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider x:Name="rangeSlider" Width="200" VerticalAlignment="Center" Minimum="0" Maximum="100" ShowRange="True" RangeStart="30" RangeEnd="90"  />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

   rangeSlider.RangeEnd = 90;

{% endhighlight %}

{% highlight VB %}

  rangeSlider.RangeEnd = 90

{% endhighlight %}

{% endtabs %}

![RangeSlider RangeEnd view](Range_images/Range_img3.jpg)





