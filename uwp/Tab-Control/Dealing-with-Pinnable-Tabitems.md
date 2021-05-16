---
layout: post
title: Dealing with Pinnable Tabitems in UWP Tab Control control | Syncfusion
description: Learn here all about Dealing with Pinnable Tabitems support in Syncfusion UWP Tab Control (SfTabControl) control and more.
platform: uwp
control: SfTabControl
documentation: ug
---

# Dealing with Pinnable Tabitems in UWP Tab Control (SfTabControl)

Tab Items in SfTabControl can be pinned or unpinned using the pin button next to its header text. 

* A pinned tab item will move to the last position in pinned tab items panel (Appears prior to unpinned items panel).
* An unpinned tab item will move to the first position in unpinned tab items panel (Appears next to pinned items panel).
* Pin (or) unpin button is visible when the item is selected or pointer is over (for unselected) the item.

## Show Pinnable Button 

To enable this feature, set the property ShowPinnableButton to true for the tab items.

The following code example and screen shot illustrate this.

{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl>

<navigation:SfTabItem Header="Paul Vent" x:Name="Paul"
                      Content="Description about Paul Vent" ShowPinnableButton="true"/>

<navigation:SfTabItem Header="Niko"
                      Content="Description about Niko" ShowPinnableButton="true"/>

<navigation:SfTabItem Header="James"
                      Content="Description about James" ShowPinnableButton="true"/>

<navigation:SfTabItem Header="Carl"
                      Content="Description about Carl" ShowPinnableButton="true"/>

</navigation:SfTabControl>


{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

Paul.ShowPinnableButton = true;

{% endhighlight %}

{% highlight VB %}

Paul.ShowPinnableButton = True

{% endhighlight %}

{% endtabs %}


![Dealing-with-Pinnable-Tabitems-img1](Dealing-with-Pinnable-Tabitems-images/Dealing-with-Pinnable-Tabitems-img1.jpeg)


## Enable scroll buttons for pinned items panel

The pinned item tab panel is scrollable. The scroll buttons can be enabled by setting the property “PinnedTabScrollButtonVisibility”.

{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl x:Name="tabControl" PinnedTabScrollButtonVisibility="Visible">

<navigation:SfTabItem Header="Paul Vent" Content="Description about Paul Vent" ShowPinnableButton="true"/>

<navigation:SfTabItem Header="Niko" Content="Description about Niko" ShowPinnableButton="true"/>

<navigation:SfTabItem Header="James" Content="Description about James" ShowPinnableButton="true"/>

<navigation:SfTabItem Header="Carl" Content="Description about Carl" ShowPinnableButton="true"/>

</navigation:SfTabControl>



{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

tabControl.PinnedTabScrollButtonVisibility = Syncfusion.UI.Xaml.Controls.Navigation.TabScrollButtonVisibility.Visible;

{% endhighlight %}

{% highlight VB %}

tabControl.PinnedTabScrollButtonVisibility = Syncfusion.UI.Xaml.Controls.Navigation.TabScrollButtonVisibility.Visible

{% endhighlight %}

{% endtabs %}

![Dealing-with-Pinnable-Tabitems-img2](Dealing-with-Pinnable-Tabitems-images/Dealing-with-Pinnable-Tabitems-img2.jpeg)


