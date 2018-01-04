---
layout: post
title: StateChanging Event of Syncfusion SfDockingManager control for UWP
description: Describtion about StateChanging Event of windows in SfDockingManager control for UWP
platform: uwp
control: SfDockingManager
documentation: ug
---

# StateChanging Event

DockStateChanging event will raise whenever the child element changing its State. StateChanging of child element can now be restricted by setting args.Cancel to true. “args” represents the event argument of DockStateChangingEventArgs for `DockStateChanging` event. The default value of args.Cancel is false. 

{% tabs %}

{% highlight XAML %}

<syncfusion:SfDockingManager Name="docking" DockStateChanging="docking_DockStateChanging">

<ContentControl syncfusion:SfDockingManager.Header="Solution Explorer"  syncfusion:SfDockingManager.SideInDockedMode="Right"  syncfusion:SfDockingManager.DesiredWidthInDockedMode="200"/>

<ContentControl syncfusion:SfDockingManager.Header="Toolbox" syncfusion:SfDockingManager.DesiredWidthInDockedMode="200"/>

<ContentControl syncfusion:SfDockingManager.Header="MainPage.xaml.cs" syncfusion:SfDockingManager.DockState="Document"/>

<ContentControl syncfusion:SfDockingManager.Header="MainPage.xaml" syncfusion:SfDockingManager.DockState="Document"/>

</syncfusion:SfDockingManager>

{% endhighlight %}

{% highlight C# %}

private void docking_DockStateChanging(object sender, DockStateChangingEventArgs args)

{

FrameworkElement element = args.TargetElement as FrameworkElement;

if (SfDockingManager.GetHeader(element) == "Toolbox")

{

args.Cancel = true;

}

}

{% endhighlight %}

{% endtabs %}


## Restricting DockingManager child element closing

State of the child element will change to `Hidden` while closing it. It can be restricted by changing the value of args.Cancel to true. The following code describes how to handle the closing of a child using DockStateChanging event.

{% tabs %}

{% highlight XAML %}

<syncfusion:SfDockingManager Name="docking" DockStateChanging="docking_DockStateChanging">

<ContentControl syncfusion:SfDockingManager.Header="Solution Explorer"  syncfusion:SfDockingManager.SideInDockedMode="Right"  syncfusion:SfDockingManager.DesiredWidthInDockedMode="200"/>

<ContentControl syncfusion:SfDockingManager.Header="Toolbox" syncfusion:SfDockingManager.DesiredWidthInDockedMode="200"/>

<ContentControl syncfusion:SfDockingManager.Header="MainPage.xaml.cs" syncfusion:SfDockingManager.DockState="Document"/>

<ContentControl syncfusion:SfDockingManager.Header="MainPage.xaml" syncfusion:SfDockingManager.DockState="Document"/>

</syncfusion:SfDockingManager>

{% endhighlight %}

{% highlight C# %}

private void docking_DockStateChanging(object sender, DockStateChangingEventArgs args)

{

if (args.NewState == DockState.Hidden)

{

args.Cancel = true;

}

}

{% endhighlight %}

{% endtabs %}
