---
layout: post
title: Getting Started with SfTileView control for UWP
description: Getting Started with SfTileView control for UWP
platform: uwp
control: SfTileView
documentation: ug
---

# Getting Started

This section explains how to create the `SfTileView` control.

## Creating SfTileView control

Create a Universal Windows project in Visual Studio and refer to the following assemblies.

1. Syncfusion. SfTileView.UWP
2. Syncfusion.SfShared.UWP

### Adding SfTileView control through XAML Code

1.Include the namespace for Syncfusion.SfTileView.UWP assembly in MainPage.xaml

{% tabs %}

{% highlight XAML %}

<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:layout="using:Syncfusion.UI.Xaml.Controls.Layout">

{% endhighlight %}

{% endtabs %}

2.Now add the `SfTileView` control with a required optimal name using the included namespace

{% tabs %}

{% highlight XAML %}

<layout:SfTileView x:Name="hubTile">

{% endhighlight %}

{% endtabs %}

### Adding SfTileView control through C# Code

1.Include the namespace for Syncfusion. SfTileView.UWP assembly in MainPage.xaml.cs

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.Controls.Layout;

{% endhighlight %}

{% endtabs %}

2.Now add the `SfTileView` control with an optimal name 

{% tabs %}

{% highlight C# %}

SfTileView tileView = new SfTileView();

{% endhighlight %}

{% endtabs %}

