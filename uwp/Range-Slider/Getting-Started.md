---
layout: post
title: Getting Started with UWP Range Slider control | Syncfusion
description: Learn here all about getting started with Syncfusion UWP Range Slider (SfRangeSlider) control and more.
platform: uwp
control: SfRange Slider 
documentation: ug
---

# Getting Started with UWP Range Slider (SfRangeSlider)

This section explains how to create `SfRangeSlider` control.

## Adding SfRangeSlider control

Create a Universal Windows Platform project in Visual Studio and refer to the following assemblies.

* Syncfusion.SfInput.UWP
* Syncfusion.SfShared.UWP

1.Include the namespace for Syncfusion.SfInput.UWP assembly in MainPage.xaml

{% tabs %}

{% highlight XAML %}

<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">

{% endhighlight %}

{% endtabs %}


2.Now add the `SfRangeSlider` control with a required optimal name using the included namespace

{% tabs %}

{% highlight XAML %}

<input:SfRangeSlider x:Name="rangeSlider"  Width="500" HorizontalAlignment="Center" VerticalAlignment="Center" Minimum="0" Maximum="100"/>

{% endhighlight %}

{% highlight C# %}

 SfRangeSlider rangeSlider = new SfRangeSlider() { Width = 500, HorizontalAlignment = HorizontalAlignment.Center, VerticalAlignment = VerticalAlignment.Center, Minimum = 0, Maximum = 100 };

{% endhighlight %}

{% highlight VB %}

  Dim rangeSlider As New SfRangeSlider() With {
	 .Width = 500,
	 .HorizontalAlignment = HorizontalAlignment.Center,
	 .VerticalAlignment = VerticalAlignment.Center,
	 .Minimum = 0,
	 .Maximum = 100
 }

{% endhighlight %}

{% endtabs %}
