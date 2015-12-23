---
layout: post
title: Getting Started with SfCalendar control for UWP
description: A quick tour to initial users on SfCalendar control for UWP
platform: uwp
control: SfCalendar
documentation: ug
---

# Getting Started

This section explains how to create the SfCalendar control.

## Creating SfCalendar control

Create a Universal Windows project in Visual Studio and refer to the following assemblies.

1. Syncfusion. SfInput.UWP

2. Syncfusion.SfShared.UWP

### Adding SfCalendar control through XAML

1.Include the namespace for Syncfusion.SfInput.UWP assembly in MainPage.xaml

{% tabs %}

{% highlight XAML %}
 
<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">

{% endhighlight %}

{% endtabs %}

2.Now add the SfCalendar control with a required optimal name using the included namespace

{% tabs %}

{% highlight XAML %}

<input:SfCalendar x:Name="calendar">

{% endhighlight %}

{% endtabs %}

### Adding SfCalendar control through C# Code

1.Include the namespace for Syncfusion. SfInput.UWP assembly in MainPage.xaml.cs

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.Controls.Input;

{% endhighlight %}

{% endtabs %}

2.Now add the SfCalendar control with a required optimal name 

{% tabs %}

{% highlight C# %}

SfCalendar calendar = new SfCalendar();

{% endhighlight %}

{% endtabs %}

## Culture support

Month and day names of a region can be displayed in SfCalendar based on the Culture property.

{% tabs %}

{% highlight XAML %}

<input:SfCalendar x:Name="calendar"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

calendar.Culture = new System.Globalization.CultureInfo("fr-FR");

{% endhighlight %}

{% endtabs %}

![](SfCalendar-images/SfCalendar-img4.jpeg)


