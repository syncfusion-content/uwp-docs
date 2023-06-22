---
layout: post
title: Getting Started with UWP Tree Navigator control | Syncfusion
description: Learn here about getting started with Syncfusion UWP Tree Navigator (SfTreeNavigator) control, its elements and more.
platform: uwp
control: SfTreeNavigator
documentation: ug
---

# Getting Started with UWP Tree Navigator (SfTreeNavigator)

This section explains how to visualize hierarchal data in tree structure using `SfTreeNavigator` control.

## Adding SfTreeNavigator control

Create a Universal Windows Platform project in Visual Studio and refer to the following assemblies.

* Syncfusion.SfTreeNavigator.UWP
* Syncfusion.SfShared.UWP

1.Include the namespace for Syncfusion.SfTreeNavigator.UWP assembly in MainPage.xaml

{% tabs %}

{% highlight XAML %}

<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:navigation="using:Syncfusion.UI.Xaml.Controls.Navigation">

{% endhighlight %}

{% endtabs %}

2.Now add the `SfTreeNavigator` control with a required optimal name using the included namespace

{% tabs %}

{% highlight XAML %}

<navigation:SfTreeNavigator x:Name="treeNavigator">

{% endhighlight %}

{% highlight C# %}

SfTreeNavigator treeNavigator = new SfTreeNavigator();

{% endhighlight %}

{% highlight VB %}

Dim treeNavigator As New SfTreeNavigator()

{% endhighlight %}

{% endtabs %}

## Setting header for SfTreeNavigator

Use `Header` property to set the header value “Enterprise Toolkit” for Tree Navigator control as given below:

{% tabs %}

{% highlight XAML %}

<navigation:SfTreeNavigator x:Name="treeNavigator" Header="Enterprise Toolkit"
                            Width="260" Height="280"/>
{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

treeNavigator.Header = "Enterprise Toolkit";

{% endhighlight %}

{% highlight VB %}

treeNavigator.Header = "Enterprise Toolkit"

{% endhighlight %}

{% endtabs %}


## Adding items to SfTreeNavigator

Add the required number of items in multiple hierarchical levels as given below to the `SfTreeNavigator` control:

{% tabs %}

{% highlight XAML %}

<navigation:SfTreeNavigator Header="Enterprise Toolkit"
                            Width="260" Height="280"
							NavigationMode="Extended">
							
<navigation:SfTreeNavigatorItem>

<navigation:SfTreeNavigatorItem/>

</navigation:SfTreeNavigatorItem>

<navigation:SfTreeNavigatorItem>

<navigation:SfTreeNavigatorItem/>

</navigation:SfTreeNavigatorItem>

<navigation:SfTreeNavigatorItem>

<navigation:SfTreeNavigatorItem/>

</navigation:SfTreeNavigatorItem>

<navigation:SfTreeNavigatorItem>

<navigation:SfTreeNavigatorItem/>

</navigation:SfTreeNavigatorItem>

<navigation:SfTreeNavigatorItem/>

<navigation:SfTreeNavigatorItem/>

</navigation:SfTreeNavigator>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

 SfTreeNavigator treeNavigator = new SfTreeNavigator();

 treeNavigator.Items.Add(new SfTreeNavigatorItem());

 treeNavigator.Items.Add(new SfTreeNavigatorItem());

 treeNavigator.Items.Add(new SfTreeNavigatorItem());

 treeNavigator.Items.Add(new SfTreeNavigatorItem());

 treeNavigator.Items.Add(new SfTreeNavigatorItem());

{% endhighlight %}

{% highlight VB %}

 Dim treeNavigator As New SfTreeNavigator()

 treeNavigator.Items.Add(New SfTreeNavigatorItem())

 treeNavigator.Items.Add(New SfTreeNavigatorItem())

 treeNavigator.Items.Add(New SfTreeNavigatorItem())

 treeNavigator.Items.Add(New SfTreeNavigatorItem())

 treeNavigator.Items.Add(New SfTreeNavigatorItem())

{% endhighlight %}

{% endtabs %}

## Setting header for the Tree Navigator Items

Set header for all the items in Tree navigator as given below:

{% tabs %}

{% highlight XAML %}

<navigation:SfTreeNavigator Header="Enterprise Toolkit"
                            Width="260" Height="280"
							NavigationMode="Extended">
							
<navigation:SfTreeNavigatorItem Header="WinRT (XAML) (20)">

<navigation:SfTreeNavigatorItem Header="Controls"/>

</navigation:SfTreeNavigatorItem>

<navigation:SfTreeNavigatorItem Header="WPF (30)">

<navigation:SfTreeNavigatorItem Header="Controls"/>

</navigation:SfTreeNavigatorItem>

<navigation:SfTreeNavigatorItem Header="Silverlight (30)">

<navigation:SfTreeNavigatorItem Header="Controls"/>

</navigation:SfTreeNavigatorItem>

<navigation:SfTreeNavigatorItem Header="Windows Phone (20)">

<navigation:SfTreeNavigatorItem Header="Controls"/>

</navigation:SfTreeNavigatorItem>

<navigation:SfTreeNavigatorItem Header="Metro Studio"/>

<navigation:SfTreeNavigatorItem Header="Orubase Studio"/>

</navigation:SfTreeNavigator>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

  SfTreeNavigator treeNavigator = new SfTreeNavigator(){Header="Enterprise Toolkit",Width=260 , Height=280,NavigationMode=NavigationMode.Extended};

  treeNavigator.Items.Add(new SfTreeNavigatorItem() { Header = "WinRT (XAML) (20)" });

  treeNavigator.Items.Add(new SfTreeNavigatorItem() { Header="Controls"});

  treeNavigator.Items.Add(new SfTreeNavigatorItem() { Header="WPF (30)"});

  treeNavigator.Items.Add(new SfTreeNavigatorItem() { Header="Controls"});

  treeNavigator.Items.Add(new SfTreeNavigatorItem() { Header="Silverlight (30)" });

{% endhighlight %}

{% highlight VB %}

Dim treeNavigator As New SfTreeNavigator() With {
	.Header="Enterprise Toolkit",
	.Width=260,
	.Height=280,
	.NavigationMode=NavigationMode.Extended
}

treeNavigator.Items.Add(New SfTreeNavigatorItem() With {.Header = "WinRT (XAML) (20)"})

treeNavigator.Items.Add(New SfTreeNavigatorItem() With {.Header="Controls"})

treeNavigator.Items.Add(New SfTreeNavigatorItem() With {.Header="WPF (30)"})

treeNavigator.Items.Add(New SfTreeNavigatorItem() With {.Header="Controls"})

treeNavigator.Items.Add(New SfTreeNavigatorItem() With {.Header="Silverlight (30)"})

{% endhighlight %}

{% endtabs %}

![Creating UWP SfTreeNavigator control](overview-images/uwp-tree-navigator-creation.jpeg)