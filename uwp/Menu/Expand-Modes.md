---
layout: post
title: Expand Modes in UWP Menu | Syncfusion®
description: Control submenu opening behavior using ExpandMode with click or mouse-over interactions in the UWP Menu control.
platform: uwp
control: SfMenu
documentation: ug
--- 

# Expand Modes in UWP Menu (SfMenu)

The `UWP Menu` provides two expand modes for opening the submenu of an `SfMenuItem`: `ExpandOnClick` and `ExpandOnMouseOver`. These modes allow the submenu to open either by clicking the menu item or by hovering the mouse over it. The expand mode can be configured using the `ExpandMode` property. By default, submenus open when the mouse hovers over an `SfMenuItem`.

## Open SubMenu on Click

Submenu of each `SfMenuItem` can be opened by clicking it when `ExpandMode` property is set to ExpandOnClick. This type of expand mode is used to open menus in the Windows operating system. Similarly, when the `ExpandMode` property is set to ExpandOnMouseOver, submenu of each `SfMenuItem` opened on moving the mouse pointer over it. `ExpandMode` can be changed as shown in the following code snippet.

{% tabs %}

{% highlight XAML %}

<menu:SfMenu  x:Name="Sfmenu"  ExpandMode="ExpandOnClick" Width="176">

<menu:SfMenuItem Header="File" StaysOpenOnClick="true" >

<menu:SfMenuItem  Header="New" />

<menu:SfMenuItem  Header="Open"/>

<menu:SfMenuItem Header="Close"/>

</menu:SfMenuItem>

<menu:SfMenuItem Header="Edit">

<menu:SfMenuItem Header="Undo"/>

<menu:SfMenuItem Header="Redo" />

<menu:SfMenuItem Header="Cut" />

<menu:SfMenuItem Header="Copy" />

</menu:SfMenuItem>

<menu:SfMenuItem Header="View">

<menu:SfMenuItem Header="Find Results" />

<menu:SfMenuItem Header="Other Windows" />

</menu:SfMenuItem> 

</menu:SfMenu>

{% endhighlight %}

{% endtabs %}

