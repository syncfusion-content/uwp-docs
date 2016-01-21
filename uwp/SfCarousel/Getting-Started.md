---
layout: post
title: Getting Started with SfCarousel control for UWP 
description: Getting Started with SfCarousel control for UWP
platform: uwp
control: SfCarousel
documentation: ug
---

# Getting Started

This section explains how to create a preview of slides using SfCarousel control.

## Creating SfCarousel control

Create a Universal Windows project in Visual Studio and refer to the following assemblies.

1. Syncfusion. SfCarousel.UWP

2. Syncfusion.SfShared.UWP

## Adding SfCarousel control

1.Include the namespace for Syncfusion.SfCarousel.UWP assembly in MainPage.xaml

{% tabs %}

{% highlight XAML %}
 
<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:layout="using:Syncfusion.UI.Xaml.Controls.Layout">

{% endhighlight %}

{% endtabs %}

2.Now add the SfCarousel control with a required optimal name using the included namespace

{% tabs %}

{% highlight XAML %}

<layout:SfCarousel x:Name="carousel">

{% endhighlight %}

{% endtabs %}

## Adding SfCarouselItems to the control

Here SfCarouselItems are added as the children of the SfCarousel.

{% tabs %}

{% highlight XAML %}

<layout:SfCarousel x:Name="carousel">

<layout:SfCarouselItem/>

<layout:SfCarouselItem/>

<layout:SfCarouselItem/>

<layout:SfCarouselItem/>

</layout:SfCarousel>

{% endhighlight %}

{% endtabs %}

## Setting content for CarouselItems

Content property helps to set the content for SfCarouselItem. `SfCarouselItem` is a ContentControl so that any object can be added as its content. Here images are set as the content of carousel items.

{% tabs %}

{% highlight XAML %}

<layout:SfCarousel x:Name="carousel">

<layout:SfCarouselItem >

<Image Source="Assets/1.jpg" Stretch="Uniform"/>

</layout:SfCarouselItem>

<layout:SfCarouselItem >

<Image Source="Assets/2.jpg" Stretch="Uniform"/>

</layout:SfCarouselItem>

<layout:SfCarouselItem >

<Image Source="Assets/3.jpg" Stretch="Uniform"/>

</layout:SfCarouselItem>

<layout:SfCarouselItem >

<Image Source="Assets/4.jpg" Stretch="Uniform"/>

</layout:SfCarouselItem>

</layout:SfCarousel>

{% endhighlight %}

{% endtabs %}

![](SfCarousel-images/SfCarousel-img1.jpeg)