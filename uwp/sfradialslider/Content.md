---
layout: post
title: Setting Content of SfRadialSlider control for UWP
description: Setting Content of SfRadialSlider control for UWP
platform: uwp
control: SfRadial Slider 
documentation: ug
---

# Content

The Content property can be used to place any content inside the Inner Rim. 

{% highlight xaml %}

<syncfusion:SfRadialSlider x:Name="rSlider1">

    <TextBlock Text="{Binding ElementName=rSlider1,Path=Value}" FontSize="24"/>

</syncfusion:SfRadialSlider>

{% endhighlight %}

![](Concepts--and-Features_images/Concepts--and-Features_img3.png)
