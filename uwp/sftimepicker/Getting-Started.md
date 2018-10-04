---
layout: post
title: Getting Started of SfTimePicker control | UWP | Syncfusion
description: Getting started section provide details about how to use the SfTimePicker control in the UWP application
platform: uwp
control: SfTimePicker
documentation: ug
---

# Getting Started

This section explains how to create the SfTimePicker control

## Adding SfTimePicker control

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

2.Now add the `SfTimePicker` control with a required optimal name using the included namespace

{% tabs %}

{% highlight XAML %}

 <syncfusion:SfTimePicker x:Name="timePicker" VerticalAlignment="Center" Width="200" Margin="15"/>

{% endhighlight %}

{% highlight C# %}

 SfTimePicker timePicker = new SfTimePicker();

{% endhighlight %}

{% highlight VB %}

 Dim timePicker As New SfTimePicker()

{% endhighlight %}

{% endtabs %}




