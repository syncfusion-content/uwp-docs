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

The `CanFloat` attached property helps to enable or disable the floating functionality by setting its value as True or False respectively. By default, its value is True, to disable this functionality turn its value to False. While setting CanFloat property as false, it disable the dragging functionality of dock window. So, we cannot change the dock window position by mouse interaction. But, DockWindow position can be changed through codebehind.

{% tabs %}

{% highlight XAML %}

<layout:SfDockingManager>

<ContentControl Name="SolutionExplorer" layout:SfDockingManager.Header="SolutionExplorer"
                layout:SfDockingManager.CanFloat="False"/>

<ContentControl Name="ToolBox" layout:SfDockingManager.Header="ToolBox"
                layout:SfDockingManager.CanFloat="False"/>
                
<ContentControl Name="ErrorList" layout:SfDockingManager.Header="ErrorList"
                layout:SfDockingManager.CanFloat="False"/>

</layout:SfDockingManager>

{% endhighlight %}

{% endtabs %}

### Change Dock Window position through codebehind

By using `SetSideInDockMode` property we can set the side and `SetTargetNameInDockedMode` property for changing the target of desired dock window.

{% tabs %}

{% highlight C# %}
 
SfDockingManager.SetSideInDockedMode(ToolBox, Dock.Tabbed);
 
SfDockingManager.SetTargetNameInDockedMode(ToolBox, "SolutionExplorer");
 
SfDockingManager.SetSideInDockedMode(ErrorList, Dock.Top);

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


