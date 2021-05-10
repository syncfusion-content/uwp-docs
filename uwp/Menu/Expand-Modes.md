---
layout: post
title: Expand Modes in UWP Menu control | Syncfusion
description: Learn here all about Expand Modes support in Syncfusion UWP Menu (SfMenu) control and more.
platform: UWP
control: SfMenu
documentation: ug
--- 

# Expand Modes in UWP Menu (SfMenu)

Expand Modes in `SfMenu` is used to open the submenu of each `SfMenuItem`, which is added in `SfMenu` by doing click to open the submenu or by doing mouse hover to open the submenu. `SfMenu` supports two kinds of Expand Modes, namely `ExpandOnClick` and `ExpandOnMouseOver` Expand Modes which can be obtained by using the `ExpandMode` property. By default submenu items opened by mouse over on `SfMenuItem`.

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

