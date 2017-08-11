---
layout: post
title: Tabbed Window of Syncfusion SfDockingManager control for UWP
description: Learn how to change the tab alignments and closing behaviour of Tabbed Window
platform: uwp
control: SfDockingManager
documentation: ug
---

# Tabbed Window

Child window can be arranged as Tabbed window by setting `TargetName` and side value as Tabbed using the property `SideInDockedMode`.

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


## Tab Alignments

By default, tabs of the docked windows are placed at bottom. To place the tabs of the docked window at different sides, set the property `DockTabPlacement` with desired values such as `Top`, `Bottom`, `Left` and `Right`.

* Setting `DockTabPlacement` as `Bottom`

{% tabs %}

{% highlight XAML %}

<syncfusion:SfDockingManager DockTabPlacement="Bottom" x:Name="dockingManager">

<ContentControl x:Name="dock1" syncfusion:SfDockingManager.Header="Item 1"
                               syncfusion:SfDockingManager.DockState="Dock">

<TextBlock Text="This is item 1 content"/>

</ContentControl>

<ContentControl syncfusion:SfDockingManager.Header="Item 2"
                syncfusion:SfDockingManager.DockState="Dock"
				syncfusion:SfDockingManager.SideInDockedMode="Tabbed"
				syncfusion:SfDockingManager.TargetNameInDockedMode="dock1">

<TextBlock Text="This is item 2 content"/>

</ContentControl>

<ContentControl syncfusion:SfDockingManager.Header="Item 3"
                syncfusion:SfDockingManager.DockState="Dock"
				syncfusion:SfDockingManager.SideInDockedMode="Tabbed"
				syncfusion:SfDockingManager.TargetNameInDockedMode="dock1">

<TextBlock Text="This is item 3 content"/>

</ContentControl>

</syncfusion:SfDockingManager>

{% endhighlight %}


{% highlight C# %}

dockingManager.DockTabPlacement = Syncfusion.UI.Xaml.Controls.Layout.TabPlacement.Bottom;

{% endhighlight %}

{% endtabs %}

![](Tabbed-Window-images/Tab-Alignments-img1.jpeg)


* Setting `DockTabPlacement` as `Top`

{% tabs %}

{% highlight XAML %}

<syncfusion:SfDockingManager DockTabPlacement="Top" x:Name="dockingManager">

<ContentControl x:Name="dock1" syncfusion:SfDockingManager.Header="Item 1"
                               syncfusion:SfDockingManager.DockState="Dock">

<TextBlock Text="This is item 1 content"/>

</ContentControl>

<ContentControl syncfusion:SfDockingManager.Header="Item 2"
                syncfusion:SfDockingManager.DockState="Dock"
				syncfusion:SfDockingManager.SideInDockedMode="Tabbed"
				syncfusion:SfDockingManager.TargetNameInDockedMode="dock1">

<TextBlock Text="This is item 2 content"/>

</ContentControl>

<ContentControl syncfusion:SfDockingManager.Header="Item 3"
                syncfusion:SfDockingManager.DockState="Dock"
				syncfusion:SfDockingManager.SideInDockedMode="Tabbed"
				syncfusion:SfDockingManager.TargetNameInDockedMode="dock1">

<TextBlock Text="This is item 3 content"/>

</ContentControl>

</syncfusion:SfDockingManager>

{% endhighlight %}

{% highlight C# %}

dockingManager.DockTabPlacement = Syncfusion.UI.Xaml.Controls.Layout.TabPlacement.Top;

{% endhighlight %}

{% endtabs %}

![](Tabbed-Window-images/Tab-Alignments-img2.jpeg)


* Setting `DockTabPlacement` as `Left`

{% tabs %}

{% highlight XAML %}

<syncfusion:SfDockingManager DockTabPlacement="Left" x:Name="dockingManager">

<ContentControl x:Name="dock1" syncfusion:SfDockingManager.Header="Item 1"
                               syncfusion:SfDockingManager.DockState="Dock">

<TextBlock Text="This is item 1 content"/>

</ContentControl>

<ContentControl syncfusion:SfDockingManager.Header="Item 2"
                syncfusion:SfDockingManager.DockState="Dock"
				syncfusion:SfDockingManager.SideInDockedMode="Tabbed"
				syncfusion:SfDockingManager.TargetNameInDockedMode="dock1">

<TextBlock Text="This is item 2 content"/>

</ContentControl>

<ContentControl syncfusion:SfDockingManager.Header="Item 3"
                syncfusion:SfDockingManager.DockState="Dock"
				syncfusion:SfDockingManager.SideInDockedMode="Tabbed"
				syncfusion:SfDockingManager.TargetNameInDockedMode="dock1">

<TextBlock Text="This is item 3 content"/>

</ContentControl>

</syncfusion:SfDockingManager>

{% endhighlight %}


{% highlight C# %}

dockingManager.DockTabPlacement= Syncfusion.UI.Xaml.Controls.Layout.TabPlacement.Left;

{% endhighlight %}

{% endtabs %}

![](Tabbed-Window-images/Tab-Alignments-img3.jpeg)


* Setting `DockTabPlacement` as `Right`

{% tabs %}

{% highlight XAML %}

<syncfusion:SfDockingManager DockTabPlacement="Right" x:Name="dockingManager">

<ContentControl x:Name="dock1" syncfusion:SfDockingManager.Header="Item 1"
                               syncfusion:SfDockingManager.DockState="Dock">

<TextBlock Text="This is item 1 content"/>

</ContentControl>

<ContentControl syncfusion:SfDockingManager.Header="Item 2"
                syncfusion:SfDockingManager.DockState="Dock"
				syncfusion:SfDockingManager.SideInDockedMode="Tabbed"
				syncfusion:SfDockingManager.TargetNameInDockedMode="dock1">

<TextBlock Text="This is item 2 content"/>

</ContentControl>

<ContentControl syncfusion:SfDockingManager.Header="Item 3"
                syncfusion:SfDockingManager.DockState="Dock"
				syncfusion:SfDockingManager.SideInDockedMode="Tabbed"
				syncfusion:SfDockingManager.TargetNameInDockedMode="dock1">

<TextBlock Text="This is item 3 content"/>

</ContentControl>

</syncfusion:SfDockingManager>

{% endhighlight %}

{% highlight C# %}

dockingManager.DockTabPlacement = Syncfusion.UI.Xaml.Controls.Layout.TabPlacement.Right;

{% endhighlight %}

{% endtabs %}

![](Tabbed-Window-images/Tab-Alignments-img4.jpeg)


