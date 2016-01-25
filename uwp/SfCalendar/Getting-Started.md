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

## Adding SfCalendar Control

Create a Universal Windows project in Visual Studio and refer to the following assemblies.

* Syncfusion. SfInput.UWP

* Syncfusion.SfShared.UWP

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

## Enabling Navigation Buttons

Set the property `ShowNavigationButton` to true for enabling the navigation buttons that allows switching between months.

{% tabs %}

{% highlight XAML %}

<input:SfCalendar x:Name="calendar" ShowNavigationButton="True"/>

{% endhighlight %}

{% endtabs %}

![](SfCalendar-images/SfCalendar-img1.jpeg)

## Culture Support

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


