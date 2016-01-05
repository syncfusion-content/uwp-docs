---
layout: post
title: Getting Started with SfTabControl control for UWP
description: A quick tour to initial users on SfTabControl control for UWP
platform: uwp
control: SfTabControl
documentation: ug
---

# Getting Started

This section explains how to create the SfTabControl control.

## Creating SfTabControl control

Create a Universal Windows project in Visual Studio and refer to the following assemblies.

1. Syncfusion. SfTabControl.UWP
2. Syncfusion.SfShared.UWP

### Adding SfTabControl control through XAML Code


1.Include the namespace for Syncfusion.SfTabControl.UWP assembly in MainPage.xaml

{% tabs %}

{% highlight XAML %}

<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:navigation="using:Syncfusion.UI.Xaml.Controls.Navigation">

{% endhighlight %}


{% endtabs %}


2.Now add the SfTabControl control with a required optimal name using the included namespace


{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl x:Name="tabControl">

{% endhighlight %}


{% endtabs %}


### Adding SfTabControl control through C# Code

1.Include the namespace for Syncfusion. SfTabControl.UWP assembly in MainPage.xaml.cs****

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.Controls.Navigation;

{% endhighlight %}

{% endtabs %}

2.Now add the SfTabControl control with an optimal name 

{% tabs %}

{% highlight C# %}

SfTabControl tabControl = new SfTabControl();

{% endhighlight %}

{% endtabs %}


