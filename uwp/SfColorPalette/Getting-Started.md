---
layout: post
title: Getting Started with SfColorPalette control for UWP
description: Getting Started with SfColorPalette control for UWP
platform: uwp
control: SfColorPalette
documentation: ug
---

# Getting Started

This section explains how to create a color palette with predefined swatches using `SfColorPalette` control.

## Creating SfColorPalette control

Create a Universal Windows project in Visual Studio and refer to the following assemblies.

1. Syncfusion. SfSfColorPickers.UWP
2. Syncfusion.SfRadialMenu.UWP
3. Syncfusion.SfShared.UWP

### Adding SfColorPalette control through XAML

1.Include the namespace for Syncfusion.SfSfColorPickers.UWP assembly in MainPage.xaml

{% tabs %}

{% highlight XAML %}

<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:media="using:Syncfusion.UI.Xaml.Controls.Media">

{% endhighlight %}

{% endtabs %}

2.Now add the `SfColorPalette` control with a required optimal name using the included namespace

{% tabs %}

{% highlight XAML %}

<media:SfColorPalette x:Name="colorPalette">

{% endhighlight %}

{% endtabs %}

### Adding SfColorPalette control through Code-behind

1.Include the namespace for Syncfusion. SfSfColorPickers.UWP assembly in MainPage.xaml.cs

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.Controls.Media;

{% endhighlight %}

{% endtabs %}

2.Now add the `SfColorPalette` control with a required optimal name 

{% tabs %}

{% highlight C# %}

SfColorPalette colorPalette = new SfColorPalette();

{% endhighlight %}

{% endtabs %}

![](SfColorPalette-images/SfColorPalette-img1.jpeg)