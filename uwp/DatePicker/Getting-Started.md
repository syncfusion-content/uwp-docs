---
layout: post
title: Getting Started with UWP DatePicker control | Syncfusion
description: Learn here about getting started with Syncfusion UWP DatePicker (SfDatePicker) control, its elements and more.
platform: uwp
control: SfDatePicker
documentation: ug
---

# Getting Started with UWP DatePicker (SfDatePicker)

This section provides a quick overview for working with [SfDatePicker](https://help.syncfusion.com/cr/uwp/Syncfusion.SfInput.UWP~Syncfusion.UI.Xaml.Controls.Input.SfDatePicker.html) control.



## Assembly deployment
Refer to the [control dependencies](https://help.syncfusion.com/uwp/control-dependencies#sfdatepicker) section to get the list of assemblies or NuGet package that needs to be added as a reference to use the[SfDatePicker](https://help.syncfusion.com/cr/uwp/Syncfusion.SfInput.UWP~Syncfusion.UI.Xaml.Controls.Input.SfDatePicker.html) control in any application.

You can refer this [documentation](https://help.syncfusion.com/uwp/visual-studio-integration/nuget-packages) to find more details about installing the NuGet package in a UWP application.

## Creating Application with SfDatePicker control
In this walk through, user will create a UWP application that contains [SfDatePicker](https://help.syncfusion.com/cr/uwp/Syncfusion.SfInput.UWP~Syncfusion.UI.Xaml.Controls.Input.SfDatePicker.html) control.
1. [Creating project](#Creating-the-project)
2. [Adding control via designer](#Adding-control-via-designer)
3. [Adding control manually in XAML](#Adding-control-manually-in-XAML)
4. [Adding control manually in C#](#Adding-control-manually-in-C#)

## Creating project 
Below section provides detailed information to create new project in Visual Studio to display [SfDatePicker](https://help.syncfusion.com/cr/uwp/Syncfusion.SfInput.UWP~Syncfusion.UI.Xaml.Controls.Input.SfDatePicker.html) control.

## Adding control via designer
The[SfDatePicker](https://help.syncfusion.com/cr/uwp/Syncfusion.SfInput.UWP~Syncfusion.UI.Xaml.Controls.Input.SfDatePicker.html) control can be added to the application by dragging it from Toolbox and dropping it in designer. The required assembles will be added automatically.

![Adding control via designer](getting-started_images/getting-started-img1.png)

## Adding control manually in XAML

In order to add [SfDatePicker](https://help.syncfusion.com/cr/uwp/Syncfusion.SfInput.UWP~Syncfusion.UI.Xaml.Controls.Input.SfDatePicker.html) control manually in XAML, do the below steps,

1. Add the below required assembly references to the project,

    * Syncfusion.SfInput.UWP
    * Syncfusion.SfShared.UWP

2. Include the namespace for Syncfusion.SfInput.UWP assembly in MainPage.XAML.

{% tabs %}

{% highlight XAML %}

<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:syncfusion="using:Syncfusion.UI.Xaml.Controls.Input">

{% endhighlight %}

{% endtabs %}

3. Now add the[SfDatePicker](https://help.syncfusion.com/cr/uwp/Syncfusion.SfInput.UWP~Syncfusion.UI.Xaml.Controls.Input.SfDatePicker.html) control in MainPage.XAML.

{% tabs %}

{% highlight XAML %}

<syncfusion:SfDatePicker Name="datePicker1" HorizontalAlignment="Center"  Height="30" Width="150" />

{% endhighlight %}

{% endtabs %}

## Adding control manually in C#

In order to add [SfDatePicker](https://help.syncfusion.com/cr/uwp/Syncfusion.SfInput.UWP~Syncfusion.UI.Xaml.Controls.Input.SfDatePicker.html) control manually in C#, do the below steps,

1. Add the below required assembly references to the project,

    * Syncfusion.SfInput.UWP
    * Syncfusion.SfShared.UWP

2. Import SfDatePicker namespace **Syncfusion.UI.Xaml.Controls.Input**.

3. Create SfDatePicker control instance and add it to the page.

{% tabs %}

{% highlight C# %}

SfDatePicker datePicker1 = new SfDatePicker()
{
    Height = 30,
    Width = 150,
    HorizontalAlignment = HorizontalAlignment.Center
};

{% endhighlight %}

{% highlight VB %}

Dim datePicker1 As SfDatePicker = New SfDatePicker() With {
    .Height = 30,
    .Width = 150,
    .HorizontalAlignment = HorizontalAlignment.Center
}

{% endhighlight %}

{% endtabs %}

![Adding control via XAML or code](getting-started_images/getting-started-img3.png)

## Customizing the date format

The format of date in [SfDatePicker](https://help.syncfusion.com/cr/uwp/Syncfusion.SfInput.UWP~Syncfusion.UI.Xaml.Controls.Input.SfDatePicker.html) can be be customized by using [FormatString](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.Input.SfTimePicker.html#Syncfusion_UI_Xaml_Controls_Input_SfTimePicker_FormatString) property. For example, format of date can be changed to *yyyy-dd-MM* format.

{% tabs %}

{% highlight XAML %}

<syncfusion:SfDatePicker HorizontalAlignment="Center" VerticalAlignment="Center" FormatString="yyyy-dd-MM"  Width="125" />

{% endhighlight %}
{% highlight C# %}

datePicker1.FormatString = "yyyy-dd-MM";

{% endhighlight %}

{% highlight VB %}

datePicker1.FormatString = "yyyy-dd-MM"

{% endhighlight %}

{% endtabs %}

![FormatString in SfDatePicker](Getting-Started_images/Getting-Started-img3.png)

## Customize SfDateSelector Header

You can customize the [SfDateSelector](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.Input.SfDateSelector.html) in [SfDatePicker](https://help.syncfusion.com/cr/uwp/Syncfusion.SfInput.UWP~Syncfusion.UI.Xaml.Controls.Input.SfDatePicker.html) control using [SelectorStyle](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.Input.SfTimePicker.html#Syncfusion_UI_Xaml_Controls_Input_SfTimePicker_SelectorStyle) property.

{% tabs %}

{% highlight XAML %}

<syncfusion:SfDatePicker HorizontalAlignment="Center" VerticalAlignment="Center" FormatString="M"  Width="125">
    <syncfusion:SfDatePicker.SelectorStyle>
        <Style TargetType="syncfusion:SfDateSelector">
            <Setter Property="Header" Value="Set your alarm" />
        </Style>
    </syncfusion:SfDatePicker.SelectorStyle>
</syncfusion:SfDatePicker>

{% endhighlight %}

{% endtabs %}

![customizing SfDateSelector header](getting-started_images/getting-started-img4.png)

