---
layout: post
title: Content Template of SfRadialSlider control for UWP
description: Content Template of SfRadialSlider control for UWP
platform: uwp
control: SfRadial Slider 
documentation: ug
---

# Content Template

The ContentTemplate  property can be used to customize the content of the SfRadialSlider. 

{% highlight xaml %}

  <syncfusion:SfRadialSlider

            Content="{Binding RelativeSource={RelativeSource Self}, Path=Value}"

            x:Name="rSlider1">

            <syncfusion:SfRadialSlider.ContentTemplate>

                <DataTemplate>

                  <TextBlock Text="{Binding}" FontSize="24" Foreground="LightSkyBlue"/>

                </DataTemplate>

            </syncfusion:SfRadialSlider.ContentTemplate>

  </syncfusion:SfRadialSlider>

{% endhighlight %}

![](Concepts--and-Features_images/Concepts--and-Features_img4.png)
