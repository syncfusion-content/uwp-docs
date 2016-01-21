---
layout: post
title:  Getting Started with SfCalculator control for UWP 
description:  Getting Started with SfCalculator control for UWP
platform: uwp
control: SfCalculator
documentation: ug
---

# Getting Started

This section explains how to create a standalone calculator control that provide options to perform basic arithmetic operations.

## Creating SfCalculator control

Create a Universal Windows project in Visual Studio and refer to the following assemblies.

1. Syncfusion. SfInput.UWP

2. Syncfusion.SfShared.UWP

## Adding SfCalculator control

1.Include the namespace for Syncfusion.SfInput.UWP assembly in MainPage.xaml

{% tabs %}

{% highlight XAML %}
 
<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">

{% endhighlight %}

{% endtabs %}

2.Now add the `SfCalculator` control with a required optimal name using the included namespace

{% tabs %}

{% highlight XAML %}

<input:SfCalculator x:Name="calculator">

{% endhighlight %}

{% endtabs %}

Above code example creates the calculator as follows and perform mathematical arithmetic operations using the provided buttons:

![](SfCalculator-images/SfCalculator-img1.jpeg)