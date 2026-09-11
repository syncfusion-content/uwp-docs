---
layout: post
title: Content Template in UWP Radial Slider | Syncfusion®
description: Customize content displayed in the UWP Radial Slider (SfRadialSlider) control using the ContentTemplate property and data-bound values.
platform: uwp
control: SfRadial Slider 
documentation: ug
---

# Content Template in UWP Radial Slider (SfRadialSlider)

The ContentTemplate  property can be used to customize the content of the UWP Radial or Circular Slider. 

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

![Concepts--and-Features_img4](Concepts--and-Features_images/Concepts--and-Features_img4.png)
