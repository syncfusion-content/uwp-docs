---
layout: post
title: Getting Started with UWP DateTimePicker control | Syncfusion
description: Learn here all about getting started with Syncfusion UWP DateTimePicker (SfDateTimeCombo) control and more.
platform: uwp
control: SfDateTimeCombo
documentation: ug
---

# Getting Started with UWP DateTimePicker (SfDateTimeCombo)

This section explains how to create SfDateTimeCombo control

## Add SfDateTimeCombo to an application

Create a Universal Windows Platform project in Visual Studio and refer to the following assemblies.

* Syncfusion.SfInput.UWP

* Syncfusion.SfShared.UWP

1.Include the namespace for Syncfusion.SfInput.UWP assembly in MainPage.xaml
  
{% tabs %}

{% highlight XAML %}
 
<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:syncfusion="using:Syncfusion.UI.Xaml.Controls.Input">

{% endhighlight %}

{% endtabs %}

 2.Now add the `SfDateTimeCombo` control with a required optimal name using the included namespace

{% tabs %}

{% highlight xaml %}
	
 <syncfusion:SfDateTimeCombo x:Name="datetimeCombo" FormatString="Mdy"  Width="430"  HorizontalAlignment="Left"/>
 
{% endhighlight %}

{% highlight C# %}
	
 SfDateTimeCombo datetimeCombo = new SfDateTimeCombo() { FormatString = "Mdy", Width = 430, HorizontalAlignment = HorizontalAlignment.Left };
 
{% endhighlight %}

{% highlight VB %}
	
Dim datetimeCombo As New SfDateTimeCombo() With {
	.FormatString = "Mdy",
	.Width = 430,
	.HorizontalAlignment = HorizontalAlignment.Left
}
 
{% endhighlight %}

{% endtabs %}