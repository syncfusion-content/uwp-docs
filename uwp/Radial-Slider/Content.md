---
layout: post
title: Content in UWP Radial Slider control | Syncfusion
description: Learn here all about Content support in Syncfusion UWP Radial Slider (SfRadialSlider) control and more.
platform: uwp
control: SfRadial Slider 
documentation: ug
---

# Content in UWP Radial Slider (SfRadialSlider)

The Content property can be used to place any content inside the Inner Rim. 

{% highlight xaml %}

<syncfusion:SfRadialSlider x:Name="rSlider1">

    <TextBlock Text="{Binding ElementName=rSlider1,Path=Value}" FontSize="24"/>

</syncfusion:SfRadialSlider>

{% endhighlight %}

![Concepts--and-Features_img3](Concepts--and-Features_images/Concepts--and-Features_img3.png)
