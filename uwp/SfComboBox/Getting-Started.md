---
layout: post
title:  Getting Started with SfComboBox control for UWP 
description:  Getting Started with SfComboBox control for UWP 
platform: uwp
control: SfComboBox  
documentation: ug
---

# Getting Started 

This section explains how to create a long list of items using SfComboBox control.

## Adding SfComboBox control

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

2.Now add the `SfComboBox` control with a required optimal name using the included namespace

{% tabs %}

{% highlight XAML %}

<input:SfComboBox x:Name="combobox">

{% endhighlight %}

{% highlight C# %}

SfComboBox combobox = new SfComboBox();

{% endhighlight %}

{% highlight VB %}

Dim combobox As New SfComboBox()

{% endhighlight %}

{% endtabs %}
