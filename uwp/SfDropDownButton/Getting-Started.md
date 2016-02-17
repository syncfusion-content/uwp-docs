---
layout: post
title: Getting Started documentation of the SfDropDownButton control for UWP
description: Getting Started documentation of the SfDropDownButton control for UWP
platform: uwp
control:  SfDropDownButton
documentation: ug
---
# Getting Started

This section explains how to create the SfDropDownButton control.

## Creating SfDropDownButton control

Create a Universal Windows project in Visual Studio and refer to the following assemblies.

1. Syncfusion. SfInput.UWP
2. Syncfusion.SfShared.UWP



###  Adding SfDropDownButton control through XAML Code


1. Include the namespace for Syncfusion. SfInput.UWP assembly in MainPage.xaml

{% highlight xml %}

<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">


{% endhighlight %}

2. Now add the SfDropDownButton control with a required optimal name using the included namespace

{% highlight xml %}

<input:SfDropDownButton x:Name="dropDownButton"/>

{% endhighlight %}

### Adding SfDropDownButton control through C# Code

1. Include the namespace for Syncfusion. SfInput.UWP assembly in MainPage.xaml.cs

{% highlight c# %}

using Syncfusion.UI.Xaml.Controls.Input;

{% endhighlight %}

2. Now add the SfDropDownButton control with an optimal name 

{% highlight c# %}

SfDropDownButton dropDownButton = new SfDropDownButton();

{% endhighlight %}

This will create an empty SfDropDownButton control.

![](Getting-Started_images/Getting-Started_img1.jpeg)


