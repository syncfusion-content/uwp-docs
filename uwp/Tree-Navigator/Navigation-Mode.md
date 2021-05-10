---
layout: post
title: Navigation Mode in UWP Tree Navigator control | Syncfusion
description: Learn here all about Navigation Mode support in Syncfusion UWP Tree Navigator (SfTreeNavigator) control and more.
platform: uwp
control: SfTreeNavigator
documentation: ug
---

# Navigation Mode in UWP Tree Navigator (SfTreeNavigator)

`SfTreeNavigator` supports two different modes to support navigation. They are:

* Default 
* Extended

## Default Expansion

The header of current hierarchy level item is displayed at the top of the `SfTreeNavigator` with a back button. This back button is used to navigate back towards the root from current level.

{% tabs %}

{% highlight XAML %}

<navigation:SfTreeNavigator NavigationMode="Default" x:Name="treeNavigator">

<navigation:SfTreeNavigatorItem Header="WPF">

<navigation:SfTreeNavigatorItem Header="Chart"/>

<navigation:SfTreeNavigatorItem Header="Grid"/>

<navigation:SfTreeNavigatorItem Header="Tools"/>

</navigation:SfTreeNavigatorItem>

<navigation:SfTreeNavigatorItem Header="Silverlight" />

<navigation:SfTreeNavigatorItem Header="Windows Phone"/>

<navigation:SfTreeNavigatorItem Header="WinRT"/>

<navigation:SfTreeNavigatorItem Header="Universal"/>

</navigation:SfTreeNavigator>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

treeNavigator.NavigationMode = Syncfusion.UI.Xaml.Controls.Navigation.NavigationMode.Default;

{% endhighlight %}

{% highlight VB %}

treeNavigator.NavigationMode = Syncfusion.UI.Xaml.Controls.Navigation.NavigationMode.Default

{% endhighlight %}

{% endtabs %}

![Default Expansion](Navigation-Mode-images/Navigation-Mode-img1.jpeg)

## Stacked Expansion

The header of each level from root to current level is stacked one after another at the top of the `SfTreeNavigator`. Clicking on the stacked header, navigates to the corresponding level.

{% tabs %}

{% highlight XAML %}

<navigation:SfTreeNavigator NavigationMode="Extended" x:Name="treeNavigator">

<navigation:SfTreeNavigatorItem Header="WPF">

<navigation:SfTreeNavigatorItem Header="Chart"/>

<navigation:SfTreeNavigatorItem Header="Grid"/>

<navigation:SfTreeNavigatorItem Header="Tools"/>

</navigation:SfTreeNavigatorItem>

<navigation:SfTreeNavigatorItem Header="Silverlight" />

<navigation:SfTreeNavigatorItem Header="Windows Phone"/>

<navigation:SfTreeNavigatorItem Header="WinRT"/>

<navigation:SfTreeNavigatorItem Header="Universal"/>

</navigation:SfTreeNavigator>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

treeNavigator.NavigationMode = Syncfusion.UI.Xaml.Controls.Navigation.NavigationMode.Extended;

{% endhighlight %}

{% highlight VB %}

treeNavigator.NavigationMode = Syncfusion.UI.Xaml.Controls.Navigation.NavigationMode.Extended

{% endhighlight %}

{% endtabs %}

![Stacked Expansion](Navigation-Mode-images/Navigation-Mode-img2.jpeg)


