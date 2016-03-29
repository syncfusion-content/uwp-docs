---
layout: post
title: Getting Started documentation of SfDatePicker control for UWP
description: Getting Started documentation of SfDatePicker control for UWP
platform: uwp
control: SfDatePicker
documentation: ug
---

# Getting Started

This section explains how to create the SfDatePicker control

## Adding SfDatePicker control

Create a Universal Windows project in Visual Studio and refer to the following assemblies.

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

2.Now add the `SfDatePicker` control with a required optimal name using the included namespace

{% tabs %}

{% highlight XAML %}

<input:SfDatePicker x:Name="datePicker" VerticalAlignment="Center" Width="200" Margin="15"/>

{% endhighlight %}

{% highlight C# %}

 SfDatePicker datePicker = new SfDatePicker() { VerticalAlignment = VerticalAlignment.Center, Width = 200, Margin = new Thickness(15) };

{% endhighlight %}

{% highlight VB %}

Dim datePicker As New SfDatePicker() With {.VerticalAlignment = VerticalAlignment.Center,.Width = 200,.Margin = New Thickness(15)}

{% endhighlight %}

{% endtabs %}


