---
layout: post
title: Getting Started with SfBusyIndicator control for UWP
description: Getting Started with SfBusyIndicator control for UWP
platform: uwp
control: SfBusyIndicator
documentation: ug
---

# Getting Started

This section explains how to create `SfBusyIndicator` control.

## Creating SfBusyIndicator control

Create a Universal Windows project in Visual Studio and refer to the following assemblies.

1. Syncfusion.SfBusyIndicator.UWP

2. Syncfusion.SfShared.UWP

### Adding SfBusyIndicator control through XAML

1.Include the namespace for Syncfusion.SfBusyIndicator.UWP assembly in MainPage.xaml

{% tabs %}

{% highlight XAML %}
 
<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:notification="using:Syncfusion.UI.Xaml.Controls.Notification">

{% endhighlight %}

{% endtabs %}

2.Now add the `SfBusyIndicator` control with a required optimal name using the included namespace

{% tabs %}

{% highlight XAML %}

<notification:SfBusyIndicator x:Name="busyIndicator">

{% endhighlight %}

{% endtabs %}

### Adding SfBusyIndicator control through C# code

1.Include the namespace for Syncfusion.SfBusyIndicator.UWP assembly in MainPage.xaml.cs

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.Controls.Notification;

{% endhighlight %}

{% endtabs %}

2.Now add the `SfBusyIndicator` control with a required optimal name 

{% tabs %}

{% highlight C# %}

SfBusyIndicator busyIndicator = new SfBusyIndicator();

{% endhighlight %}

{% endtabs %}