---
layout: post
title: Appearance and Styling in UWP Tab Control control | Syncfusion®
description: Learn here all about Appearance and Styling support in Syncfusion® UWP Tab Control (SfTabControl) control and more.
platform: UWP
control: SfTabControl
documentation: ug
---

# Appearance and Styling in UWP Tab Control (SfTabControl)

## Customizing item header

The header of tab item can be customized using the HeaderTemplate property. HeaderTemplateSelector property is also available to pick a data template using selection logic.

{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl>

<navigation:SfTabItem Header="Paul Vent" Content="Description about Paul Vent">

<navigation:SfTabItem.HeaderTemplate>

<DataTemplate>

<TextBlock Text="{Binding}" FontStyle="Italic"/>

</DataTemplate>

</navigation:SfTabItem.HeaderTemplate>

</navigation:SfTabItem>

<navigation:SfTabItem Header="Niko" Content="Description about Niko" />

<navigation:SfTabItem Header="James" Content="Description about James" />

<navigation:SfTabItem Header="Carl" Content="Description about Carl" />

</navigation:SfTabControl>


{% endhighlight %}


{% endtabs %}


![Appearance-and-Styling-img1](Appearance-and-Styling-images/Appearance-and-Styling-img1.jpeg)


## Customizing content transitions

Transition effects of selecting an item can be customized using ContentTransitions property.

{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl x:Name="tabControl">

<navigation:SfTabControl.ContentTransitions>

<TransitionCollection>

<EntranceThemeTransition FromHorizontalOffset="100">

</EntranceThemeTransition>

</TransitionCollection>

</navigation:SfTabControl.ContentTransitions>

</navigation:SfTabControl>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

tabControl.ContentTransitions = new Windows.UI.Xaml.Media.Animation.TransitionCollection();

tabControl.ContentTransitions.Add(new EntranceThemeTransition() { FromHorizontalOffset = 100.0 });

{% endhighlight %}

{% highlight VB %}

tabControl.ContentTransitions = New Windows.UI.Xaml.Media.Animation.TransitionCollection()

tabControl.ContentTransitions.Add(New EntranceThemeTransition() With {.FromHorizontalOffset = 100.0})

{% endhighlight %}

{% endtabs %}

## TabControlHorizontalTemplate

Template of the SfTabControl can be modified using TabControlHorizontalTemplate property in horizontal orientation.

## TabControlVerticalTemplate

Template of the SfTabControl can be modified using TabControlVerticalTemplate property in vertical orientation.

