---
layout: post
title: Getting Started with UWP DropDown Button | Syncfusion®
description: Learn how to get started with the Syncfusion® UWP DropDown Button (SfDropDownButton) control. Explore setup, features, examples, and customization options.

platform: uwp
control:  SfDropDownButton
documentation: ug
---
# Getting Started with UWP DropDown Button (SfDropDownButton)

This section explains how to create the UWP DropDown Button control.

## Creating UWP DropDown Button control

Create a Universal Windows Platform project in Visual Studio and refer to the following assemblies.

1. Syncfusion. SfInput.UWP
2. Syncfusion.SfShared.UWP



###  Adding UWP DropDown Button control through XAML Code



1.Include the namespace for Syncfusion. SfInput.UWP assembly in MainPage.xaml

{% highlight xml %}

<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">


{% endhighlight %}


2.Now add the UWP DropDown Button control with a required optimal name using the included namespace

{% highlight xml %}

<input:SfDropDownButton x:Name="dropDownButton"/>

{% endhighlight %}

### Adding UWP DropDown Button control through C# Code

1.Include the namespace for Syncfusion. SfInput.UWP assembly in MainPage.xaml.cs

{% tabs %}

{% highlight c# %}

using Syncfusion.UI.Xaml.Controls.Input;

{% endhighlight %}

{% highlight VB %}

Imports Syncfusion.UI.Xaml.Controls.Input

{% endhighlight %}

{% endtabs %}

2.Now add the UWP DropDown Button control with an optimal name 

{% tabs %}

{% highlight c# %}

SfDropDownButton dropDownButton = new SfDropDownButton();

{% endhighlight %}

{% highlight VB %}

Dim dropDownButton As New SfDropDownButton()

{% endhighlight %}

{% endtabs %}

This will create an empty UWP DropDown Button control.

![SfDropDownButton control](Getting-Started_images/Getting-Started_img1.jpeg)


