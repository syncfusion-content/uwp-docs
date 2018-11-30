---
layout: post
title: Deals with orientation to change the position of SfRangeSlider control for UWP
description: Deals with orientation to change the position of SfRangeSlider control for UWP  
platform: uwp
control: SfRange Slider 
documentation: ug
---

# Orientation  

The Orientation property has the following two options.  

1. Horizontal  
2. Vertical 

The default option is Horizontal.  

![RangeSlider Orientation Horizontal view](Orientation_images/Orientation_img1.jpg)

The following code sample shows how to set Vertical Orientation to SfRangeSlider.  

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





