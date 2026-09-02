---
layout: post
title: Getting Started with UWP Menu | Syncfusion®
description: Learn how to get started with the Syncfusion® UWP Menu (SfMenu) control. Explore setup, features, examples, and customization options.
platform: uwp
control: SfMenu
documentation: ug
--- 

# Getting Started with UWP Menu (SfMenu)

This section explains how to create the `UWP Menu` control.

## Adding UWP Menu Control

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

2.Now add the `UWP Menu` control with a required optimal name using the included namespace

{% tabs %}

{% highlight XAML %}

<menu:SfMenu  x:Name="menu">


{% endhighlight %}

{% endtabs %}

## Adding SfMenuItems to the Control

Here `SfMenuItems` are added as the children of the `UWP Menu`.

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

