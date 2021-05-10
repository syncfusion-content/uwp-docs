---
layout: post
title: Getting Started with UWP Calendar control | Syncfusion
description: Learn here all about getting started with Syncfusion UWP Calendar (SfCalendar) control and more.
platform: uwp
control: SfCalendar
documentation: ug
---

# Getting Started with UWP Calendar (SfCalendar)

This section explains how to create the SfCalendar control.

## Adding SfCalendar Control

Create a Universal Windows Platform project in Visual Studio and refer to the following assemblies.

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

{% highlight C# %}

SfCalendar calendar = new SfCalendar();

{% endhighlight %}

{% highlight VB %}

Dim calendar As New SfCalendar()

{% endhighlight %}

{% endtabs %}

## Enabling Navigation Buttons

Set the property `ShowNavigationButton` to true for enabling the navigation buttons that allows switching between months.

{% tabs %}

{% highlight XAML %}

<input:SfCalendar x:Name="calendar" ShowNavigationButton="True"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

 calendar.ShowNavigationButton = true;

{% endhighlight %}

{% highlight VB %}

 calendar.ShowNavigationButton = True

{% endhighlight %}

{% endtabs %}

![Calendar with navigation buttons](SfCalendar-images/SfCalendar-img1.jpeg)

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

{% highlight VB %}

calendar.Culture = New System.Globalization.CultureInfo("fr-FR")

{% endhighlight %}

{% endtabs %}

![Cuture support in calendar](SfCalendar-images/SfCalendar-img4.jpeg)


