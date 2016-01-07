---
layout: post
title: Getting Started with SfGridSplitter control for UWP
description: Getting Started with SfGridSplitter control for UWP
platform: uwp
control: SfGridSplitter
documentation: ug
---

# Getting Started

This section explains how to create the `SfGridSplitter` control.

## Creating SfGridSplitter control

Create a Universal Windows project in Visual Studio and refer to the following assemblies.

1. Syncfusion. SfInput.UWP
2. Syncfusion.SfShared.UWP

### Adding SfGridSplitter control through XAML Code

1.Include the namespace for Syncfusion. SfInput.UWP assembly in MainPage.xaml

{% tabs %}

{% highlight XAML %}

<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">

{% endhighlight %}

{% endtabs %}

2.Now add the `SfGridSplitter` control with a required optimal name using the included namespace

{% tabs %}

{% highlight XAML %}

<input:SfGridSplitter x:Name="gridSplitter">

{% endhighlight %}

{% endtabs %}

### Adding SfGridSplitter control through C# Code

1.Include the namespace for Syncfusion. SfInput.UWP assembly in MainPage.xaml.cs

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.Controls.Input;

{% endhighlight %}

{% endtabs %}

2.Now add the `SfGridSplitter` control with an optimal name 

{% tabs %}

{% highlight C# %}

SfGridSplitter gridSplitter = new SfGridSplitter();

{% endhighlight %}

{% endtabs %}

This will just display a horizontally placed grid splitter, which does not allow any resize operations.

![](Getting-Started-images/Getting-Started-img1.jpeg)


