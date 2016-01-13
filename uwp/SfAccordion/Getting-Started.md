---
layout: post
title: Getting Started with SfAccordion control for UWP
description: A quick tour to initial users on SfAccordion control for UWP
platform: uwp
control: SfAccordion
documentation: ug
---

# Getting Started

This section explains how to create `SfAccordion` control.

## Creating SfAccordion control

Create a Universal Windows project in Visual Studio and refer to the following assemblies.

1. Syncfusion.SfAccordion.UWP

2. Syncfusion.SfShared.UWP

### Adding SfAccordion control through XAML

1.Include the namespace for Syncfusion.SfAccordion.UWP assembly in MainPage.xaml

{% tabs %}

{% highlight XAML %}

<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:layout="using:Syncfusion.UI.Xaml.Controls.Layout">

{% endhighlight %}

{% endtabs %}

2.Now add the `SfAccordion` control with a required optimal name using the included namespace

{% tabs %}

{% highlight XAML %}

<layout:SfAccordion x:Name="accordion">

{% endhighlight %}

{% endtabs %}

### Adding SfAccordion control through C#

1.Include the namespace for Syncfusion.SfAccordion.UWP assembly in MainPage.xaml.cs

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.Controls.Layout;

{% endhighlight %}

{% endtabs %}

2.Now add the `SfAccordion` control with a required optimal name 

{% tabs %}

{% highlight C# %}

SfAccordion accordion = new SfAccordion();

{% endhighlight %}

{% endtabs %}
