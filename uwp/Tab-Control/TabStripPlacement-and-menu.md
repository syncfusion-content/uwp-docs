---
layout: post
title: TabStripPlacement and Menu in UWP Tab Control control | Syncfusion®
description: Learn here all about TabStripPlacement and Menu support in Syncfusion® UWP Tab Control (SfTabControl) control and more.
platform: uwp
control: SfTabControl
documentation: ug
---

# TabStripPlacement and Menu in UWP Tab Control (SfTabControl)

## Change placement of Tabs

The tab strip of SfTabControl can be aligned in all the four sides of SfTabControl using the TabStripPlacement property. It has the following options and by default it is top:

* Left
* Top
* Right
* Bottom

{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl x:Name="tabControl" TabStripPlacement="Bottom">

<navigation:SfTabItem Header="Paul Vent" Content="Description about Paul Vent"/>

<navigation:SfTabItem Header="Niko" Content="Description about Niko"/>

<navigation:SfTabItem Header="James" Content="Description about James"/>

<navigation:SfTabItem Header="Carl" Content="Description about Carl"/>

</navigation:SfTabControl>


{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

tabControl.TabStripPlacement = Syncfusion.UI.Xaml.Controls.Navigation.TabStripPlacement.Bottom;


{% endhighlight %}

{% highlight VB %}

tabControl.TabStripPlacement = Syncfusion.UI.Xaml.Controls.Navigation.TabStripPlacement.Bottom

{% endhighlight %}

{% endtabs %}

![TabStripPlacement-and-menu-img1](TabStripPlacement-and-menu-images/TabStripPlacement-and-menu-img1.jpeg)


## TabStripMenu

Tab strip menu is a list containing the collection of tab item headers displayed at the end of TabPanel. Any tab item can be selected using this menu.

### ShowTabStripMenu

To enable/disable this menu set the property ShowTabStripMenu in SfTabControl

{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl x:Name="tabControl" ShowTabstripMenu="true">

<navigation:SfTabItem Header="Paul Vent" Content="Description about Paul Vent"/>

<navigation:SfTabItem Header="Niko" Content="Description about Niko"/>

<navigation:SfTabItem Header="James" Content="Description about James"/>

<navigation:SfTabItem Header="Carl" Content="Description about Carl"/>

</navigation:SfTabControl>


{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

tabControl.ShowTabstripMenu = true;

{% endhighlight %}

{% highlight VB %}

tabControl.ShowTabstripMenu = True

{% endhighlight %}

{% endtabs %}

![TabStripPlacement-and-menu-img2](TabStripPlacement-and-menu-images/TabStripPlacement-and-menu-img2.jpeg)


### Adding custom items to TabStrip menu

Custom menu items can be added to the tab strip menu using TabStripMenuItems property as follows:

{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl x:Name="tabControl" ShowTabstripMenu="true">

<navigation:SfTabItem Header="Paul Vent" Content="Description about Paul Vent"/>

<navigation:SfTabItem Header="Niko" Content="Description about Niko"/>

<navigation:SfTabItem Header="James" Content="Description about James"/>

<navigation:SfTabItem Header="Carl" Content="Description about Carl"/>

</navigation:SfTabControl>


{% endhighlight %}


{% endtabs %}


{% tabs %}

{% highlight C# %}

tabControl.TabstripMenuItems = new List<object>();

tabControl.TabstripMenuItems.Add("Custom");


{% endhighlight %}

{% highlight VB %}

tabControl.TabstripMenuItems = New List(Of Object)()

tabControl.TabstripMenuItems.Add("Custom")


{% endhighlight %}

{% endtabs %}

![TabStripPlacement-and-menu-img3](TabStripPlacement-and-menu-images/TabStripPlacement-and-menu-img3.jpeg)


### Customizing TabStrip menu item

Tab strip menu items can be customized using the TabStripMenuItemTemplate property. 

{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl ShowTabstripMenu="true">

<navigation:SfTabItem Header="Paul Vent" Content="Description about Paul Vent"/>

<navigation:SfTabItem Header="Niko" Content="Description about Niko"/>

<navigation:SfTabItem Header="James" Content="Description about James"/>

<navigation:SfTabItem Header="Carl" Content="Description about Carl"/>

<navigation:SfTabControl.TabstripMenuItemTemplate>

<DataTemplate>

<TextBlock Text="{Binding}" Foreground="Red"/>

</DataTemplate>

</navigation:SfTabControl.TabstripMenuItemTemplate>

</navigation:SfTabControl>


{% endhighlight %}


{% endtabs %}

![TabStripPlacement-and-menu-img4](TabStripPlacement-and-menu-images/TabStripPlacement-and-menu-img4.jpeg)


