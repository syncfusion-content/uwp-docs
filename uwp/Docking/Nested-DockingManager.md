---
layout: post
title: Nested DockingManager in UWP SfDockingManager | Syncfusion®
description: Learn how to add a Nested DockingManager as a child window to another SfDockingManager in the Syncfusion® UWP SfDockingManager control.
platform: uwp
control: SfDockingManager
documentation: ug
---

# Nested DockingManager in UWP SfDockingManager

`SfDockingManager` provides the Nested DockingManager support, which allows adding `SfDockingManager` as a child window to another `SfDockingManager`.

{% tabs %}

{% highlight XAML %}

<layout:SfDockingManager x:Name="DockingManager1" layout:SfDockingManager.Header="Dock1">

<ContentControl x:Name="Content1" layout:SfDockingManager.Header="Dock1"/>

<layout:SfDockingManager x:Name="DockingManager2" layout:SfDockingManager.DockState="Dock"
                         layout:SfDockingManager.SideInDockedMode="Left"
                         layout:SfDockingManager.Header="Dock2"  >

<ContentControl layout:SfDockingManager.Header="Dock2"
                layout:SfDockingManager.DesiredWidthInDockedMode="600" />

</layout:SfDockingManager>

<layout:SfDockingManager x:Name="DockingManager3"
                         layout:SfDockingManager.DockState="Dock"
                         layout:SfDockingManager.SideInDockedMode="Bottom"
						 layout:SfDockingManager.Header="Dock3">

<ContentControl layout:SfDockingManager.Header="Dock3"
                layout:SfDockingManager.DesiredWidthInDockedMode="600"/>

</layout:SfDockingManager>

</layout:SfDockingManager>

{% endhighlight %}

{% endtabs %}

![Nested-DockingManager-img1](Nested-DockingManager-images/Nested-DockingManager-img1.jpeg)


