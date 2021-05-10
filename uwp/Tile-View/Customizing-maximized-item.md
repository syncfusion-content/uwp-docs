---
layout: post
title: Customizing Maximized Item in UWP Tile View control | Syncfusion
description: Learn here all about Customizing Maximized Item support in Syncfusion UWP Tile View (SfTileView) control and more.
platform: uwp
control: SfTileView
documentation: ug
---

# Customizing Maximized Item in UWP Tile View (SfTileView)

`SfTileView` provides several properties for customizing the maximized item.

## Changing maximized item height

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

{% highlight VB %}

tileView.MaximizedItemHeight = 400.0

{% endhighlight %}

{% endtabs %}

![Customizing-maximized-item-img1](Customizing-maximized-item-images/Customizing-maximized-item-img1.jpeg)

## Changing maximized item width

`MaximizedItemWidth` property is used to set width for the maximized item.

{% tabs %}

{% highlight XAML %}

<layout:SfTileView x:Name="tileView" MaximizedItemWidth="400">

</layout:SfTileView>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

tileView.MaximizedItemWidth = 400.0;

{% endhighlight %}

{% highlight VB %}

tileView.MaximizedItemWidth = 400.0

{% endhighlight %}

{% endtabs %}

![Customizing-maximized-item-img2](Customizing-maximized-item-images/Customizing-maximized-item-img2.jpeg)

## Animating maximized content

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

{% highlight VB %}

tileView.MaximizedItemHeight = 400.0

tileView.Transitions = New TransitionCollection()

tileView.Transitions.Add(New PopupThemeTransition())

{% endhighlight %}

{% endtabs %}

## Customizing maximized item

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

![Customizing-maximized-item-img3](Customizing-maximized-item-images/Customizing-maximized-item-img3.jpeg)


