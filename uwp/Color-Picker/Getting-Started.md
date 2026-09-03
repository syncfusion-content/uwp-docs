---
layout: post
title: Getting Started with UWP SfColorPicker | Syncfusion®
description: Learn how to get started with the Syncfusion® UWP SfColorPicker control. Explore setup, features, examples, and customization options.
platform: uwp
control: SfColorPicker
documentation: ug
---

# Getting Started with UWP Color Picker

This section explains how to create a RGB color model picker using the `UWP Color Picker` control.

## Creating UWP Color Picker Control

Create a Universal Windows Platform project in Visual Studio and refer to the following assemblies.

1. Syncfusion.SfColorPickers.UWP

2. Syncfusion.SfRadialMenu.UWP

3. Syncfusion.SfShared.UWP

### Adding UWP Color Picker Control through XAML

1.Include the namespace for Syncfusion.SfSfColorPickers.UWP assembly in MainPage.xaml

{% tabs %}

{% highlight XAML %}

<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:media="using:Syncfusion.UI.Xaml.Controls.Media">

{% endhighlight %}

{% endtabs %}

2.Now add the `UWP Color Picker` control with a required optimal name using the included namespace

{% tabs %}

{% highlight XAML %}

<media:SfColorPicker x:Name="colorPicker">

{% endhighlight %}

{% endtabs %}

### Adding UWP Color Picker Control through Code-Behind

1.Include the namespace for Syncfusion. SfSfColorPickers.UWP assembly in MainPage.xaml.cs

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.Controls.Media;

{% endhighlight %}

{% highlight VB %}

Imports Syncfusion.UI.Xaml.Controls.Media

{% endhighlight %}

{% endtabs %}

2.Now add the UWP Color Picker control with a required optimal name 

{% tabs %}

{% highlight C# %}

SfColorPicker colorPicker = new SfColorPicker();

{% endhighlight %}

{% highlight VB %}

Dim colorPicker As New SfColorPicker()

{% endhighlight %}

{% endtabs %}

![Overview of SfColorPicker control](Overview-images/Overview-img1.jpeg)