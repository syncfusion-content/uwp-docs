---
layout: post
title: Getting Started with SfRating control for UWP
description: A quick tour to initial users on SfRating control for UWP
platform: uwp
control: SfRating
documentation: ug
---

# Getting Started

This section explains how to create the `SfRating` control.

## Creating SfRating control

Create a Universal Windows project in Visual Studio and refer to the following assemblies.

1. Syncfusion. SfInput.UWP
2. Syncfusion.SfShared.UWP

### Adding SfRating control through XAML Code


1.Include the namespace for Syncfusion.SfInput.UWP assembly in MainPage.xaml

{% tabs %}

{% highlight XAML %}

<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">

{% endhighlight %}

{% endtabs %}


2.Now add the `SfRating` control with a required optimal name using the included namespace

{% tabs %}

{% highlight XAML %}

<input:SfRating x:Name="rating">

{% endhighlight %}

{% endtabs %}

### Adding SfRating control through C# Code

1.Include the namespace for Syncfusion.SfInput.UWP assembly in MainPage.xaml.cs

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.Controls.Input;

{% endhighlight %}

{% endtabs %}

2.Now add the `SfRating` control with an optimal name 

{% tabs %}

{% highlight C# %}

SfRating rating = new SfRating();

{% endhighlight %}

{% endtabs %}

N> This will yield a blank output screen unless `ItemsCount` is set


