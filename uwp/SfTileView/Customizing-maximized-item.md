---
layout: post
title: Customizing maximized items of SfTileView control for UWP
description: Customizing maximized items of SfTileView control for UWP
platform: uwp
control: SfTileView
documentation: ug
---

# Customizing Maximized Item

`SfTileView` provides several properties for customizing the maximized item.

## MaximizedItemHeight

`MaximizedItemHeight` property is used to set height for the maximized item.

{% tabs %}

{% highlight XAML %}

<layout:SfTileView x:Name="tileView" MaximizedItemHeight="400">

</layout:SfTileView>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

tileView.MaximizedItemHeight = 400.0;

{% endhighlight %}

{% endtabs %}

![](Customizing-maximized-item-images/Customizing-maximized-item-img1.jpeg)

## MaximizedItemWidth

`MaximizedItemWidth` property is used to set width for the maximized item.

{% tabs %}

{% highlight XAML %}

<layout:SfTileView x:Name="tileView" MaximizedItemWidth="400">

</layout:SfTileView>

{% endhighlight %}

{% highlight C# %}

tileView.MaximizedItemWidth = 400.0;

{% endhighlight %}

{% endtabs %}

![](Customizing-maximized-item-images/Customizing-maximized-item-img2.jpeg)

## Maximized Content Transitions

`MaximizedContentTransitions` property is used to apply a set of transitions when an item is maximized.

{% tabs %}

{% highlight XAML %}

<layout:SfTileView x:Name="tileView">

<layout:SfTileView.MaximizedContentTransitions>

<TransitionCollection>

<PopupThemeTransition/>

</TransitionCollection>

</layout:SfTileView.MaximizedContentTransitions>

</layout:SfTileView>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

tileView.MaximizedItemHeight = 400.0;

tileView.Transitions = new TransitionCollection();

tileView.Transitions.Add(new PopupThemeTransition());

{% endhighlight %}

{% endtabs %}

## Maximized ItemContainerStyle

`MaximizedItemContainerStyle` property is used to set style for the ContentControl that holds the MaximizedContent. It can be set as follows:

{% tabs %}

{% highlight XAML %}

<layout:SfTileView>

<layout:SfTileView.MaximizedItemContainerStyle>

<Style TargetType="ContentControl">

<Setter Property="Foreground" Value="Red"/>

</Style>

</layout:SfTileView.MaximizedItemContainerStyle>

<layout:SfTileViewItem Background="LightBlue" Content="PaulVent" MaximizedContent="Description about Paul"/>

<layout:SfTileViewItem Background="LightBlue" Content="James" MaximizedContent="Description about James"/>

<layout:SfTileViewItem Background="LightBlue" Content="Carl" MaximizedContent="Description about Carl"/>

<layout:SfTileViewItem Background="LightBlue" Content="Niko" MaximizedContent="Description about Niko"/>

</layout:SfTileView>

{% endhighlight %}

{% endtabs %}

![](Customizing-maximized-item-images/Customizing-maximized-item-img3.jpeg)


