---
layout: post
title: Positioning SfRangeSlider in UWP Range Slider | Syncfusion®
description: Arrange the UWP Range Slider control horizontally or vertically by configuring the Orientation property for different layouts.
platform: uwp
control: SfRange Slider 
documentation: ug
---

# Positioning SfRangeSlider in UWP Range Slider (SfRangeSlider)

The Orientation property has the following two options.  

1. Horizontal  
2. Vertical 

The default option is Horizontal.  

![RangeSlider Orientation Horizontal view](Orientation_images/Orientation_img1.jpg)

The following code sample shows how to set Vertical Orientation to UWP Range Slider.  

{% tabs %}

{% highlight xaml %}

<editors:SfRangeSlider x:Name="rangeSlider" Height="200" HorizontalAlignment="Center" Minimum="0" Maximum="100" Value="50" Orientation="Vertical"  />

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

   rangeSlider.Orientation = Orientation.Vertical;

{% endhighlight %}

{% highlight VB %}

   rangeSlider.Orientation = Orientation.Vertical

{% endhighlight %}

{% endtabs %}

![RangeSlider Orientation Vertical view](Orientation_images/Orientation_img2.jpg)





