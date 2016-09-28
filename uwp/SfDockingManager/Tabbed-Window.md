---
layout: post
title: Tabbed Window of Syncfusion SfDockingManager control for UWP
description: Learn how to change the tab alignments and closing behaviour of Tabbed Window
platform: uwp
control: SfDockingManager
documentation: ug
---

# Tabbed Window

Child window can be arranged as Tabbed windows by setting `TargetName` and side value as Tabbed using the property `SideInDockedMode`.

{% tabs %}

{% highlight XAML %}

<layout:SfDockingManager>

<ContentControl layout:SfDockingManager.Header="SolutionExplorer" Name="SolutionExplorer"
                layout:SfDockingManager.SideInDockedMode="Top"
				/>

<ContentControl layout:SfDockingManager.Header="Properties"
                layout:SfDockingManager.SideInDockedMode="Tabbed"
				layout:SfDockingManager.TargetNameInDockedMode="SolutionExplorer"/>


</layout:SfDockingManager>


{% endhighlight %}

{% endtabs %}

![](Tabbed-Window-images/Tabbed-Window-img1.jpeg)


