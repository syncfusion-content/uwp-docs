---
layout: post
title: Getting Started with UWP Menu control | Syncfusion
description: Learn here all about getting started with Syncfusion UWP Menu (SfMenu) control and more.
platform: UWP
control: SfMenu
documentation: ug
--- 

# Getting Started with UWP Menu (SfMenu)

This section explains how to create the `SfMenu` control.

## Adding SfMenu Control

Create a Universal Windows Platform project in Visual Studio and refer to the following assemblies.

* Syncfusion.SfMenu.UWP
* Syncfusion.SfShared.UWP

1.Include the namespace for Syncfusion.SfMenu.UWP assembly in MainPage.xaml

{% tabs %}

{% highlight XAML %}

<Page

xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:menu="using:Syncfusion.UI.Xaml.Controls.Navigation">


{% endhighlight %}

{% endtabs %}

2.Now add the `SfMenu` control with a required optimal name using the included namespace

{% tabs %}

{% highlight XAML %}

<menu:SfMenu  x:Name="menu">


{% endhighlight %}

{% endtabs %}

## Adding SfMenuItems to the Control

Here `SfMenuItems` are added as the children of the `SfMenu`.

{% tabs %}

{% highlight XAML %}

<menu:SfMenu  x:Name="menu">

<menu:SfMenuItem  Header="Open" />

<menu:SfMenuItem  Header="New" />

<menu:SfMenuItem  Header="Close" />

<menu:SfMenuItem  Header="Add" />

</menu:SfMenu>

{% endhighlight %}

{% endtabs %}

