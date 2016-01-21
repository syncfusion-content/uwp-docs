---
layout: post
title: Getting Started with SfTreeNavigator control for UWP
description: Getting Started with SfTreeNavigator control for UWP
platform: uwp
control: SfTreeNavigator
documentation: ug
---

# Getting Started

This section explains how to visualize hierarchal data in tree structure using `SfTreeNavigator` control.

## Adding SfTreeNavigator control
Create a Universal Windows project in Visual Studio and refer to the following assemblies.

1. Syncfusion. SfTreeNavigator.UWP
2. Syncfusion.SfShared.UWP

1.Include the namespace for Syncfusion.SfTreeNavigator.UWP assembly in MainPage.xaml

{% tabs %}

{% highlight XAML %}

<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:navigation="using:Syncfusion.UI.Xaml.Controls.Navigation">

{% endhighlight %}

{% endtabs %}

2.Now add the `SfTreeNavigator` control with a required optimal name using the included namespace

{% tabs %}

{% highlight XAML %}

<navigation:SfTreeNavigator x:Name="treeNavigator">

{% endhighlight %}

{% endtabs %}

