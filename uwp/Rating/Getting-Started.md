---
layout: post
title: Getting Started with UWP Rating control | Syncfusion
description: Learn here about getting started with Syncfusion UWP Rating (SfRating) control, its elements and more.
platform: uwp
control: SfRating
documentation: ug
---

# Getting Started with UWP Rating (SfRating)

This section explains how to create a group of visual symbols used for rating with `SfRating` control.

## Adding SfRating control

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


2.Now add the `SfRating` control with a required optimal name using the included namespace

{% tabs %}

{% highlight XAML %}

<input:SfRating x:Name="rating">

{% endhighlight %}

{% highlight C# %}

 SfRating rating = new SfRating();

{% endhighlight %}

{% highlight VB %}

 Dim rating As New SfRating()

{% endhighlight %}

{% endtabs %}

N> This will yield a blank output screen unless `ItemsCount` is set

## Set the number of items

Set the `ItemsCount` property to specify the number of rating items in control. 

{% tabs %}

{% highlight XAML %}

<input:SfRating ItemsCount="5" x:Name="rating">

<input:SfRating.Resources>

<Style TargetType="input:SfRatingItem">

<Setter Property="Padding" Value="1"/>

<Setter Property="RatedFill" Value="#FF1196CD"/>

<Setter Property="PointerOverFill" Value="#FF86BA35"/>

<Setter Property="Width" Value="35"/>

</Style>

</input:SfRating.Resources>

</input:SfRating>

{% endhighlight %}

{% endtabs %}


![Rating Step by Step control view](Overview-images/uwp-rating-overview.jpeg)
