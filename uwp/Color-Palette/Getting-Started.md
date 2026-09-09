---
layout: post
title: Getting Started with UWP SfColorPalette | Syncfusion®
description: Learn how to get started with the Syncfusion® UWP SfColorPalette control. Explore setup, features, examples, and customization options.
platform: uwp
control: SfColorPalette
documentation: ug
---

# Getting Started with UWP Color Palette

This section explains how to create a color palette with predefined swatches using `UWP Color Palette` control.

## Creating UWP Color Palette Control

Create a Universal Windows Platform project in Visual Studio and refer to the following assemblies.

1. Syncfusion.SfColorPickers.UWP
2. Syncfusion.SfRadialMenu.UWP
3. Syncfusion.SfShared.UWP

### Adding UWP Color Palette Control through XAML

1.Include the namespace for Syncfusion.SfSfColorPickers.UWP assembly in MainPage.xaml

{% tabs %}

{% highlight XAML %}

<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:media="using:Syncfusion.UI.Xaml.Controls.Media">

{% endhighlight %}

{% endtabs %}

2.Now add the `UWP Color Palette` control with a required optimal name using the included namespace

{% tabs %}

{% highlight XAML %}

<media:SfColorPalette x:Name="colorPalette">

{% endhighlight %}

{% endtabs %}

### Adding UWP Color Palette Control through Code-behind

1.Include the namespace for Syncfusion. SfSfColorPickers.UWP assembly in MainPage.xaml.cs

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.Controls.Media;

{% endhighlight %}

{% highlight VB %}

Imports Syncfusion.UI.Xaml.Controls.Media

{% endhighlight %}

{% endtabs %}

2.Now add the `UWP Color Palette` control with a required optimal name 

{% tabs %}

{% highlight C# %}

SfColorPalette colorPalette = new SfColorPalette();

{% endhighlight %}

{% highlight VB %}

Dim colorPalette As New SfColorPalette()

{% endhighlight %}

{% endtabs %}

![SfColorPalette control](SfColorPalette-images/SfColorPalette-img1.jpeg)