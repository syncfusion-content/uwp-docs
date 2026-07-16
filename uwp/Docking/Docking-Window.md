---
layout: post
title: Docking Window in UWP Docking control | Syncfusion®
description: Learn here all about Docking Window support in Syncfusion® UWP Docking (SfDockingManager) control and more.
platform: uwp
control: SfDockingManager
documentation: ug
---

# Docking Window in UWP Docking (SfDockingManager)

Docking window is one of the states of `SfDockingManager`. Since Dock is the default value, initially all the children stay as Docking Window.

![Docking-Window-img1](Docking-Window-images/Docking-Window-img1.jpeg)


## Configuring Window in Different Sides

The Five sides where the children can be docked are

* Left
* Right
* Top
* Bottom
* Tabbed

To dock four children of `SfDockingManager` to each side, set the `SideInDockedMode` property with appropriate values.

{% tabs %}

{% highlight XAML %}

<layout:SfDockingManager x:Name="docking">

<ContentControl layout:SfDockingManager.Header="Docking Left"
                layout:SfDockingManager.SideInDockedMode="Left"/>

<ContentControl layout:SfDockingManager.Header="Docking Top"
                layout:SfDockingManager.SideInDockedMode="Top"/>

<ContentControl layout:SfDockingManager.Header="Docking Right"
                layout:SfDockingManager.SideInDockedMode="Right"/>

<ContentControl layout:SfDockingManager.Header="Docking Bottom"
                layout:SfDockingManager.SideInDockedMode="Bottom"/>

</layout:SfDockingManager>

{% endhighlight %}

{% endtabs %}

![Docking-Window-img2](Docking-Window-images/Docking-Window-img2.jpeg)


## Docking Window in Various Targets

A Docking window can be docked on any side of the Target Docking Window using an attached property named `TargetNameInDockedMode`.

To set the child window as a TabbedWindow, the window should be aware of a Target window name. The following code helps to arrange children of `SfDockingManager` that target a single Docking window docked along Left, Top, Right and Tabbed.

{% tabs %}

{% highlight XAML %}

<layout:SfDockingManager>

<ContentControl layout:SfDockingManager.Header="Targeted Window" x:Name="DockingWindow1"/>

<!--Targeted to Docking Window1 on Top Side-->

<ContentControl layout:SfDockingManager.Header="Top"
                layout:SfDockingManager.SideInDockedMode="Top"
				layout:SfDockingManager.TargetNameInDockedMode="DockingWindow1"/>

<!--Targeted to DockingWindow1 on Right Side-->

<ContentControl layout:SfDockingManager.Header="Right"
                layout:SfDockingManager.SideInDockedMode="Right"
				layout:SfDockingManager.TargetNameInDockedMode="DockingWindow1"/>

<!--Targeted to DockingWindow1 on Left Side-->

<ContentControl layout:SfDockingManager.Header="Left"
                layout:SfDockingManager.SideInDockedMode="Left"
				layout:SfDockingManager.TargetNameInDockedMode="DockingWindow1"/>

<!--Targeted to DockingWindow1 to tab-->

<ContentControl layout:SfDockingManager.Header="Tabbed"
                layout:SfDockingManager.SideInDockedMode="Tabbed"
				layout:SfDockingManager.TargetNameInDockedMode="DockingWindow1"/>

</layout:SfDockingManager>



{% endhighlight %}

{% endtabs %}

![Docking-Window-img3](Docking-Window-images/Docking-Window-img3.jpeg)


## Enabling or Disabling the Header Visibility

`NoHeader` is an attached property that is used to hide the header of a Dock Window. The default value of `NoHeader` is false. To hide the Header, change the value of the `NoHeader` property to true.

{% tabs %}

{% highlight XAML %}

<layout:SfDockingManager>

<ContentControl layout:SfDockingManager.Header="Toolbox"/>

<ContentControl layout:SfDockingManager.Header="Solution Explorer"
                layout:SfDockingManager.NoHeader="true">
                
<TextBlock Text="Content of NoHeader window" FontStyle="Italic"
           Foreground="Gray" TextWrapping="Wrap"/>

</ContentControl>

</layout:SfDockingManager>

{% endhighlight %}

{% endtabs %}

![Docking-Window-img4](Docking-Window-images/Docking-Window-img4.jpeg)


## Enabling or Disabling the Dock Functionality

The `CanDock` attached property is used to enable or disable the docking functionality by setting its value as true or false. By default, the `CanDock` value is true. This functionality can be disabled by setting its value as false.

{% tabs %}

{% highlight XAML %}

<layout:SfDockingManager>

<ContentControl layout:SfDockingManager.Header="Toolbox"
                layout:SfDockingManager.CanDock="false"/>

</layout:SfDockingManager>

{% endhighlight %}

{% endtabs %}
