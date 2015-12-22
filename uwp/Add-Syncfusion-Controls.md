---
layout: post
title: Steps to add Syncfusion Essential UWP controls
description: Learn how to add Syncfusion Essential UWP control to the application
platform: uwp
control: Add Syncfusion Controls
documentation: ug
---

# Add Syncfusion Controls

Syncfusion UWP controls can be added in Visual Studio project in either of the following ways,

* Through Designer
* Through Code-Behind

## Through Designer


Syncfusion controls for UWP are added automatically to the Visual Studio toolbox during the Essential Studio for UWP installation. The following steps help to add Essential UWP control through drag and drop from toolbox. 

For example: SfTextBoxExt

1. Create a Universal Windows project in Visual Studio.

2. Find `SfTextBoxExt` by typing the text “SfTextBoxExt” in search box.

![](Add-Syncfusion-Controls_images/Add-Syncfusion-Controls_img1.jpeg)


3.Drag `SfTextBoxExt` from toolbox and drop it in the designer.

![](Add-Syncfusion-Controls_images/Add-Syncfusion-Controls_img2.jpeg)


## Through XAML

The following steps help to add Essential UWP control through XAML Code.

For example: SfTextBoxExt

1.Create a Universal Windows project in Visual Studio and refer the following assemblies.

 * Syncfusion.SfInput.WPF.dll
 * Syncfusion.SfShared.WPF.dll

2.Include xml namespace for the above assemblies in MainPage.xaml.

{% tabs %}
	
{% highlight XAML  %}

<Page xmlns="(http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">



{% endhighlight %}

{% endtabs %}

3.Add `SfTextBoxExt` control with an optimal name, using the included namespace.

{% tabs %}

{% highlight XAML %}

<input:SfTextBoxExt x:Name="sftextboxExt">



{% endhighlight %}

{% endtabs %}


## Through Code-Behind

The following steps help to add Essential UWP control through C# code. 
For example: SfTextBoxExt.

1.Create a WPF project in Visual Studio and refer to the following assemblies.

 * Syncfusion.SfInput.WPF.dll
 * Syncfusion.SfShared.WPF.dll

2.Create an instance of `SfTextBoxExt` using its namespace and set the required properties.

{% tabs %}

{% highlight C# %}


Syncfusion.UI.Xaml.Controls.Input.SfTextBoxExt textBoxExt1 = new Syncfusion.UI.Xaml.Controls.Input.SfTextBoxExt();

textBoxExt1.Height = 20;

textBoxExt1.Width = 120;

textBoxExt1.Margin = new Thickness(10, 10, 10, 10);

textBoxExt1.VerticalAlignment = VerticalAlignment.Center;

textBoxExt1.HorizontalAlignment = HorizontalAlignment.Center;



{% endhighlight %}

{% highlight VB %}
 
Dim textBoxExt1 As New Syncfusion.UI.Xaml.Controls.Input.SfTextBoxExt()

textBoxExt1.Height = 20

textBoxExt1.Width = 120

textBoxExt1.Margin = New Thickness(10, 10, 10, 10)

textBoxExt1.VerticalAlignment = VerticalAlignment.Center

textBoxExt1.HorizontalAlignment = HorizontalAlignment.Center



{% endhighlight %}

{% endtabs %}

3.Add the created instance to the parent window (or the needed layout panels).

{% tabs%}

{% highlight C# %}


this.Content = textBoxExt1;


{% endhighlight %}


{% highlight VB %}

Me.Content = textBoxExt1


{% endhighlight %}

{% endtabs %}

N> Syncfusion controls for UWP package can be added (available under Universal Windows => Extensions tab in Add reference dialog) in the cases of using most of the controls from Syncfusion toolkit.

