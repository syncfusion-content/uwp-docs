---
layout: post
title: Float Window of Syncfusion SfDockingManager control for UWP
description: This topic deals with float window features and how to position the float window
platform: uwp
control: SfDockingManager
documentation: ug
---

# Floating Window

Floating window is one of the state in the `SfDockingManager`. To make children of the `SfDockingManager` as Float, set its `DockState` values as Float.

{% tabs %}

{% highlight XAML %}

<layout:SfDockingManager>

<ContentControl layout:SfDockingManager.Header="SolutionExplorer"
                layout:SfDockingManager.DockState="Float"/>

</layout:SfDockingManager>

{% endhighlight %}

{% endtabs %}

![](Floating-Window-images/Floating-Window-img1.jpeg)


## Enabling or Disabling the Float functionality

The `CanFloat` attached property helps to enable or disable the floating functionality by setting its value as True or False respectively. By default, its value is True, to disable this functionality turn its value to False.

{% tabs %}

{% highlight XAML %}

<layout:SfDockingManager>

<ContentControl layout:SfDockingManager.Header="SolutionExplorer"
                layout:SfDockingManager.CanFloat="False"/>

</layout:SfDockingManager>

{% endhighlight %}

{% endtabs %}

## Positioning on Desire Location

The `FloatWindow` can be placed at any desired location. To position the `FloatWindow` at the desired location with the required rectangle bounds, call `SetFloatingWindowRect` method of the `SfDockingManager`.

{% tabs %}

{% highlight XAML %}

<layout:SfDockingManager x:Name="docking">

<ContentControl x:Name="child1" layout:SfDockingManager.Header="SolutionExplorer"
                                layout:SfDockingManager.DockState="Float"/>

</layout:SfDockingManager>

{% endhighlight %}

{% highlight C# %}

SfDockingManager.SetFloatingWindowRect(child1, new Rect(200, 0, 200, 200));

{% endhighlight %}

{% endtabs %}

![](Floating-Window-images/Floating-Window-img2.jpeg)


