---
layout: post
title: Animation Support in UWP Menu control | Syncfusion®
description: Learn here all about Animation Support support in Syncfusion® UWP Menu (SfMenu) control and more.
platform: UWP
control: SfMenu
documentation: ug
--- 

# Animation Support in UWP Menu (SfMenu)

`SfMenu` supports animation types to open the submenu pop-up. The following animation types are supported by `SfMenu`:

* Fade
* Slide
* Scroll
* None

Default 'PopUpAnimationType' is None.

## Adding the Animation Support to an Application


The opening and closing of submenu popup animation can be changed by  `PopUpAnimationType` property. If the `PopUpAnimationType` property is set to None, the submenu will open without any animation. 

The Animation support can be added to an application, as shown in the following code snippet.

{% tabs %}

{% highlight XAML %}

<menu:SfMenu  x:Name="Sfmenu" PopUpAnimationType="Slide"  >

<menu:SfMenuItem Header="File" >

<menu:SfMenuItem  Header="New" />

<menu:SfMenuItem  Header="Open" />

<menu:SfMenuItem Header="Close" />

</menu:SfMenuItem>

<menu:SfMenuItem Header="Edit">

<menu:SfMenuItem Header="Undo" />

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

