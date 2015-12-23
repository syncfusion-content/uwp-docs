---
layout: post
title:  Getting Started with SfCalculator control for UWP 
description:  Getting Started with SfCalculator control for UWP
platform: uwp
control: SfCalculator
documentation: ug
---

# Getting Started

This section explains how to create the `SfCalculator` control.

## Creating SfCalculator control

Create a Universal Windows project in Visual Studio and refer to the following assemblies.

1. Syncfusion. SfInput.UWP

2. Syncfusion.SfShared.UWP

### Adding SfCalculator control through XAML

1.Include the namespace for Syncfusion.SfInput.UWP assembly in MainPage.xaml

{% tabs %}

{% highlight XAML %}
 
<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">

{% endhighlight %}

{% endtabs %}

2.Now add the `SfCalculator` control with a required optimal name using the included namespace

{% tabs %}

{% highlight XAML %}

<input:SfCalculator x:Name="calculator">

{% endhighlight %}

{% endtabs %}

### Adding SfCalculator control through C# Code

1.Include the namespace for Syncfusion. SfInput.UWP assembly in MainPage.xaml.cs

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.Controls.Input;

{% endhighlight %}

{% endtabs %}

2.Now add the SfCalculator control with a required optimal name 

{% tabs %}

{% highlight C# %}

SfCalculator accordion = new SfCalculator();

{% endhighlight %}

{% endtabs %}