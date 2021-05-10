---
layout: post
title: Getting Started with UWP Progress Bar control | Syncfusion
description: Learn here all about getting started with Syncfusion UWP Progress Bar (SfProgressBar) control and more.
platform: UWP
control: SfProgressBar
documentation: ug
--- 

# Getting Started with UWP Progress Bar (SfProgressBar)

This section explains how to convey the task progress in an application using SfProgressBar control. 

## Adding SfProgressBar Control

Create a Universal Windows Platform project in Visual Studio and refer to the “Syncfusion.SfProgressBar.UWP” assembly.

1.Include the namespace ”Syncfusion.UI.Xaml.Controls.Notification” for Syncfusion.SfProgressBar.UWP assembly in MainPage.xaml

{% tabs %}

{% highlight XAML %}

<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:notification="using:Syncfusion.UI.Xaml.Controls.Notification">

{% endhighlight %}

{% endtabs %}

2.Now add the `SfProgressBar` control with a required optimal name using the included namespace

{% tabs %}

{% highlight XAML %}

<notification:SfProgressBar x:Name="progressBar"/>

{% endhighlight %}

{% endtabs %}

## Choosing Progress Type

Select a type from the available built-in progress bar types and set it using `ProgressType` property.

{% tabs %}

{% highlight XAML %}

<notification:SfProgressBar x:Name="progressBar" ProgressType="SolidCircular"  />

{% endhighlight %}

{% endtabs %}

## Displaying Percentage Value

Set the property `DisplayContentMode` to Percentage for enabling text displaying percentage completed.

{% tabs %}

{% highlight XAML %}

<notification:SfProgressBar x:Name="progressBar" ProgressType="SolidCircular"  DisplayContentMode="Percentage"/>

{% endhighlight %}

{% endtabs %}

## Progress Animation using Value

Here is an example using DispatcherTimer to set the Value property in specified interval.

{% tabs %}

{% highlight XAML %}

<notification:SfProgressBar x:Name="progressBar" ProgressType="SolidCircular"  DisplayContentMode="Percentage"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

public sealed partial class MainPage : Page

{

DispatcherTimer timer = new DispatcherTimer() { Interval = TimeSpan.FromSeconds(0.1) };



public MainPage()

{

this.InitializeComponent();

timer.Tick += timer_Tick;

timer.Start();

}



void timer_Tick(object sender, object e)

{

if(progressBar.Value <=100.0)

progressBar.Value += 1.0;

else
{

timer.Stop();

timer.Tick -= timer_Tick;

}

}

}

{% endhighlight %}

{% endtabs %}

