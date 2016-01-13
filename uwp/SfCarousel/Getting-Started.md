---
layout: post
title: Getting Started with SfCarousel control for UWP 
description: Getting Started with SfCarousel control for UWP
platform: uwp
control: SfCarousel
documentation: ug
---

# Getting Started

This section explains how to create the `SfCarousel` control.

## Creating SfCarousel control

Create a Universal Windows project in Visual Studio and refer to the following assemblies.

1. Syncfusion. SfCarousel.UWP

2. Syncfusion.SfShared.UWP

### Adding SfCarousel control through XAML Code

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

### Adding SfCarousel control through C# Code

1.Include the namespace for Syncfusion. SfCarousel.UWP assembly in MainPage.xaml.cs

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.Controls.Layout;

{% endhighlight %}

{% endtabs %}

2.Now add the SfCarousel control with a required optimal name 

{% tabs %}

{% highlight C# %}

SfCarousel carousel = new SfCarousel();

{% endhighlight %}

{% endtabs %}