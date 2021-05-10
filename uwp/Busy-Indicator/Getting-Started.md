---
layout: post
title: Getting Started with UWP Busy Indicator control | Syncfusion
description: Learn here all about getting started with Syncfusion UWP Busy Indicator (SfBusyIndicator) control and more.
platform: uwp
control: SfBusyIndicator
documentation: ug
---

# Getting Started with UWP Busy Indicator (SfBusyIndicator)

This section explains how to create a visual representation indicating background running process with animation using `SfBusyIndicator` control.

## Adding SfBusyIndicator Control


Create a Universal Windows Platform project in Visual Studio and refer to the "Syncfusion.SfBusyIndicator.UWP" assembly.

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

{% highlight C# %}

SfBusyIndicator busyIndicator = new SfBusyIndicator();

{% endhighlight %}

{% highlight VB %}

Dim busyIndicator As New SfBusyIndicator()

{% endhighlight %}

{% endtabs %}

![Animation Winmil](SfBusyIndicator1/Winrt.png)

## Choosing Animation

Choose an animation from the available built-in animations and set it using `AnimationType` property.

{% tabs %}

{% highlight XAML %}
 
<Grid Background="CornFlowerBlue"/>

<notification:SfBusyIndicator AnimationType="Gear"/>

</Grid>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}
 
SfBusyIndicator busyIndicator = new SfBusyIndicator() { AnimationType = AnimationTypes.Gear };

{% endhighlight %}

{% highlight VB %}
 
Dim busyIndicator As New SfBusyIndicator() With {.AnimationType = AnimationTypes.Gear}

{% endhighlight %}

{% endtabs %}

![Animation Gear](SfBusyIndicator1/Gear.png)

## Setting Busy Header

Set the `Header` property with text “Loading…” to display a busy status and customize the header with `HeaderTemplate` property as given below:

{% tabs %}

{% highlight XAML %}
 
<Grid Background="CornFlowerBlue"/>

<notification:SfBusyIndicator Header="Loading..."/>

</Grid>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}
 
SfBusyIndicator busyIndicator = new SfBusyIndicator() { Header="Loading..." };

{% endhighlight %}

{% highlight VB %}
 
 Dim busyIndicator As New SfBusyIndicator() With {.Header="Loading..."}

{% endhighlight %}

{% endtabs %}

![Provide the Header Text](SfBusyIndicator1/Load.png)

 