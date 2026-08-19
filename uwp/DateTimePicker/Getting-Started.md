---
layout: post
title: Getting Started with UWP DateTimePicker | Syncfusion
description: Learn how to get started with the Syncfusion UWP DateTimePicker control. Explore setup, features, examples, and customization options.
platform: uwp
control: SfDateTimeCombo
documentation: ug
---

# Getting Started with UWP DateTimePicker

This section explains how to create the SfDateTimeCombo control.

## Add SfDateTimeCombo to an application

Create a Universal Windows Platform project in Visual Studio and refer to the following assemblies.

* Syncfusion.SfInput.UWP

* Syncfusion.SfShared.UWP

1. Include the namespace for Syncfusion.SfInput.UWP assembly in MainPage.xaml
  
{% tabs %}

{% highlight XAML %}
 
<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:syncfusion="using:Syncfusion.UI.Xaml.Controls.Input">

{% endhighlight %}

{% endtabs %}

2. Now add the `SfDateTimeCombo` control with a required name using the included namespace

{% tabs %}

{% highlight XAML %}

<Page
   ...
   xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">

    <syncfusion:SfDateTimeCombo x:Name="datetimeCombo" FormatString="Mdy"  Width="430"  HorizontalAlignment="Left"/>

</Page>

{% endhighlight %}

{% highlight C# %}

using Syncfusion.UI.Xaml.Controls.Input;

 SfDateTimeCombo datetimeCombo = new SfDateTimeCombo() { FormatString = "Mdy", Width = 430, HorizontalAlignment = HorizontalAlignment.Left };
 
{% endhighlight %}

{% highlight VB %}

Imports Syncfusion.UI.Xaml.Controls.Input;

Dim datetimeCombo As New SfDateTimeCombo() With {
	.FormatString = "Mdy",
	.Width = 430,
	.HorizontalAlignment = HorizontalAlignment.Left
}
 
{% endhighlight %}

{% endtabs %}