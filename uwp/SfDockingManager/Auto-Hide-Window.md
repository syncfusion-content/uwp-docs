---
layout: post
title: AutoHide Window of Syncfusion SfDockingManager control for UWP
description: Learn how to customize SidePanel, SideTabItem and change pinning behaviour of AutoHide window
platform: uwp
control: SfDockingManager
documentation: ug
---

# Auto Hide Window

`AutoHide` window is one of the state in the `SfDockingManager`. To enable Auto hidden for SfDockingManager’s children, set its `DockState` value as `AutoHidden`.

![](Auto-Hide-Window-images/Auto-Hide-Window-img1.jpeg)


## Configuring Window in Different Side

`AutoHidden` window can be placed in four different sides such as Top, Bottom, Left and Right. To place the four auto hidden children in four different sides, set `SideInDockedMode` property according to its corresponding values in the `SfDockingManager`.

{% tabs %}

{% highlight XAML %}

<layout:SfDockingManager>

<ContentControl layout:SfDockingManager.Header="Top" x:Name="AutoHideWindow1"
                layout:SfDockingManager.DockState="AutoHidden"
				layout:SfDockingManager.SideInDockedMode="Top" />

<ContentControl layout:SfDockingManager.Header="Left" x:Name="AutoHideWindow2"
                layout:SfDockingManager.DockState="AutoHidden"
				layout:SfDockingManager.SideInDockedMode="Left" />

<ContentControl layout:SfDockingManager.Header="Right" x:Name="AutoHideWindow3"
                layout:SfDockingManager.DockState="AutoHidden"
				layout:SfDockingManager.SideInDockedMode="Right" />

<ContentControl layout:SfDockingManager.Header="Bottom" x:Name="AutoHideWindow4"
                layout:SfDockingManager.DockState="AutoHidden"
				layout:SfDockingManager.SideInDockedMode="Bottom" />

</layout:SfDockingManager>

{% endhighlight %}

{% endtabs %}

![](Auto-Hide-Window-images/Auto-Hide-Window-img2.jpeg)


## Side Panel and TabItem Customization

The side panel and side panel header can be customized through `SideTabBackground`, `SideItemsBackground` and `SideItemsForeground` properties of the `SfDockingManager`.

{% tabs %}

{% highlight XAML %}

<layout:SfDockingManager SideTabBackground="Brown"
                         SideItemsForeground="White" SideItemsBackground="Green">

<ContentControl layout:SfDockingManager.Header="SolutionExplorer"
                layout:SfDockingManager.DockState="AutoHidden" />

<ContentControl layout:SfDockingManager.Header="ToolBox" />

</layout:SfDockingManager>

{% endhighlight %}

{% endtabs %}

![](Auto-Hide-Window-images/Auto-Hide-Window-img3.jpeg)


### Scrollable Panel

Side panel have scroll support when Auto Hidden tab items overflow onto the side panel.

## Configuring AutoHide Animation

The Animation speed while auto hiding a window can be configured by setting required time delay in `AutoHideAnimationSpeed` property.

{% tabs %}

{% highlight XAML %}

<layout:SfDockingManager AutoHideAnimationSpeed="400">

<ContentControl layout:SfDockingManager.Header="SolutionExplorer"
                layout:SfDockingManager.DockState="AutoHidden" />

</layout:SfDockingManager>

{% endhighlight %}

{% endtabs %}

## Making Different Animations for AutoHide window

`SfDockingManager` supports three different built–in animations while auto-hiding the windows such as Fade, Scale and Slide that can be set through the property `AutoHideAnimationMode`.

`Fade` – AutoHidden Window fades while auto hiding

{% tabs %}

{% highlight XAML %}

<layout:SfDockingManager AutoHideAnimationMode="Fade">

<ContentControl layout:SfDockingManager.Header="SolutionExplorer"
                layout:SfDockingManager.DockState="AutoHidden" />

</layout:SfDockingManager>

{% endhighlight %}

{% endtabs %}

`Scale` – AutoHidden Window scale while auto hiding

{% tabs %}

{% highlight XAML %}

<layout:SfDockingManager AutoHideAnimationMode="Scale">

<ContentControl layout:SfDockingManager.Header="SolutionExplorer"
                layout:SfDockingManager.DockState="AutoHidden" />

</layout:SfDockingManager>

{% endhighlight %}

{% endtabs %}

`Slide` – AutoHidden Window slides while auto hiding

{% tabs %}

{% highlight XAML %}

<layout:SfDockingManager AutoHideAnimationMode="Slide">

<ContentControl layout:SfDockingManager.Header="SolutionExplorer"
                layout:SfDockingManager.DockState="AutoHidden" />

</layout:SfDockingManager>

{% endhighlight %}

{% endtabs %}

## Enabling and Disabling the AutoHide functionality

The Pin button that performs Auto Hide functionality can be visible by default. It can be invisible to disable the AutoHide functionality through `ShowAwlButton` property.

{% tabs %}

{% highlight XAML %}

<layout:SfDockingManager ShowAwlButton="False">

<ContentControl layout:SfDockingManager.Header="SolutionExplorer" />

</layout:SfDockingManager>

{% endhighlight %}

{% endtabs %}

![](Auto-Hide-Window-images/Auto-Hide-Window-img4.jpeg)


To show or collapse the AutoHide button for a specific child in the `SfDockingManager`, `AwlButtonVisible` attached property can be used. By default, its value is true, this functionality can be disabled by setting its value as false.

{% tabs %}

{% highlight XAML %}

<layout:SfDockingManager>

<ContentControl layout:SfDockingManager.Header="SolutionExplorer"
                layout:SfDockingManager.AwlButtonVisible="False"/>

<ContentControl layout:SfDockingManager.Header="ToolBox"
                layout:SfDockingManager.AwlButtonVisible="True"/>

</layout:SfDockingManager>

{% endhighlight %}

{% endtabs %}

![](Auto-Hide-Window-images/Auto-Hide-Window-img5.jpeg)


To enable or disable the AutoHide functionality for a specific child in the `SfDockingManager`, `CanAutoHide` attached property can be used. By default, its value is true, this functionality can be disabled by setting its value as false.

{% tabs %}

{% highlight XAML %}

<layout:SfDockingManager>

<ContentControl layout:SfDockingManager.Header="SolutionExplorer"
                layout:SfDockingManager.CanAutoHide="False"/>

<ContentControl layout:SfDockingManager.Header="ToolBox"
                layout:SfDockingManager.CanAutoHide="True"/>

</layout:SfDockingManager>

{% endhighlight %}

{% endtabs %}