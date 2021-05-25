---
layout: post
title: Getting Started with UWP Radial Menu control | Syncfusion
description: Learn here about getting started with Syncfusion UWP Radial Menu (SfRadialMenu) control, its elements and more.
platform: uwp
control: SfRadial Menu 
documentation: ug
---

# Getting Started with UWP Radial Menu (SfRadialMenu)

Namespace : Syncfusion.UI.Xaml.Controls.Navigation 

Assembly : Syncfusion.SfRadialMenu.UWP

Dependent assembly: Syncfusion.SfShared.UWP

The following code sample shows how to create the SfRadialMenu from code-behind and XAML. 
{% tabs %}
{% highlight xaml %}
<Page xmlns:navigation="using:Syncfusion.UI.Xaml.Controls.Navigation"> 
     <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">
	 <navigation:SfRadialMenu> 
     <navigation:SfRadialMenuItem Header="Bold"/>
	 <navigation:SfRadialMenuItem Header="Cut"/> 
     <navigation:SfRadialMenuItem Header="Copy"/>
	 <navigation:SfRadialMenuItem Header="Paste"/> 
     </navigation:SfRadialMenu>
	 </Grid> 
</Page>
{% endhighlight %}

{% highlight c# %}
 SfRadialMenu radialMenu = new SfRadialMenu();
 SfRadialMenuItem bold = new SfRadialMenuItem(){ Header = "Bold" };  
 SfRadialMenuItem cut = new SfRadialMenuItem() { Header = "Cut" };
 SfRadialMenuItem copy = new SfRadialMenuItem() { Header = "Copy" };
 SfRadialMenuItem paste = new SfRadialMenuItem() { Header = "Paste" };
 radialMenu.Items.Add(bold);
 radialMenu.Items.Add(cut);
 radialMenu.Items.Add(copy);
 radialMenu.Items.Add(paste);

 {% endhighlight %}
 
 {% highlight VB %}
 
 Dim radialMenu As New SfRadialMenu()
 Dim bold As New SfRadialMenuItem() With {.Header = "Bold"}
 Dim cut As New SfRadialMenuItem() With {.Header = "Cut"}
 Dim copy As New SfRadialMenuItem() With {.Header = "Copy"}
 Dim paste As New SfRadialMenuItem() With {.Header = "Paste"}
 radialMenu.Items.Add(bold)
 radialMenu.Items.Add(cut)
 radialMenu.Items.Add(copy)
 radialMenu.Items.Add(paste)

 {% endhighlight %}

{% endtabs %}
