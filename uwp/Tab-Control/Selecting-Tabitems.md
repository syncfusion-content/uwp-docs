---
layout: post
title: Selecting Items in UWP Tab Control control | Syncfusion®
description: Learn here all about Selecting Items support in Syncfusion® UWP Tab Control (SfTabControl) control and more.
platform: uwp
control: SfTabControl
documentation: ug
---

# Selecting Items in UWP Tab Control (SfTabControl)

SfTabControl can have only one selected item at a time. Tab items can be selected by 

* Touching the header text of SfTabItem 
* Using tab strip/list menu
* Programmatically using the properties SelectedItem, SelectedIndex, IsSelected

## Selecting item through Tab strip menu

Tab strip menu is a list containing the collection of tab item headers displayed at the end of TabPanel. Any tab item can be selected using this menu. To enable/disable this menu set the property ShowTabStripMenu in SfTabControl.

## Selecting item using SelectedItem

SelectedItem property is used to select an item using its instance.

{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl SelectedItem="niko" x:Name="tabControl">

<navigation:SfTabItem Header="Paul Vent" Content="Description about Paul Vent"/>

<navigation:SfTabItem x:Name="Niko" Header="Niko" Content="Description about Niko"/>

<navigation:SfTabItem Header="James" Content="Description about James"/>

<navigation:SfTabItem Header="Carl" Content="Description about Carl"/>

</navigation:SfTabControl>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

tabControl.SelectedItem = Niko;

{% endhighlight %}

{% highlight VB %}

tabControl.SelectedItem = Niko

{% endhighlight %}

{% endtabs %}

![Selecting-Tabitems-img1](Selecting-Tabitems-images/Selecting-Tabitems-img1.jpeg)


## Selecting item using SelectedIndex

SelectedIndex property is used to select an item using its index.

{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl SelectedIndex="1" x:Name="tabControl">

<navigation:SfTabItem Header="Paul Vent" Content="Description about Paul Vent"/>

<navigation:SfTabItem Header="Niko" Content="Description about Niko"/>

<navigation:SfTabItem Header="James" Content="Description about James"/>

<navigation:SfTabItem Header="Carl" Content="Description about Carl"/>

</navigation:SfTabControl>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

tabControl.SelectedIndex = 1;

{% endhighlight %}

{% highlight VB %}

tabControl.SelectedIndex = 1

{% endhighlight %}

{% endtabs %}

![Selecting-Tabitems-img2](Selecting-Tabitems-images/Selecting-Tabitems-img2.jpeg)


## Selecting item using IsSelected

IsSelected property is used to check whether an item is selected or not. An item can also be selected by setting its IsSelected to true.

{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl>

<navigation:SfTabItem Header="Paul Vent" Content="Description about Paul Vent"/>

<navigation:SfTabItem x:Name="Niko" IsSelected="true"
                      Header="Niko" Content="Description about Niko"/>

<navigation:SfTabItem Header="James" Content="Description about James"/>

<navigation:SfTabItem Header="Carl" Content="Description about Carl"/>

</navigation:SfTabControl>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

Niko.IsSelected = true;

{% endhighlight %}

{% highlight VB %}

Niko.IsSelected = True

{% endhighlight %}

{% endtabs %}

## Selection change by Swipe Gestures

`SfTabControl` SelectedItem can be changed by Swipe Gestures. This can be enabled by set `EnableSwipeGestures` property of SfTabControl as true. By default, `EnableSwipeGestures` value is false.

{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl EnableSwipeGestures ="true">

<navigation:SfTabItem Header="Paul Vent" Content="Description about Paul Vent"/>

<navigation:SfTabItem x:Name="niko" IsSelected="true"
                      Header="Niko" Content="Description about Niko"/>

<navigation:SfTabItem Header="James" Content="Description about James"/>

<navigation:SfTabItem Header="Carl" Content="Description about Carl"/>

</navigation:SfTabControl>

{% endhighlight %}

{% endtabs %}

![Selecting-Tabitems-img3](Selecting-Tabitems-images/Selecting-Tabitems-img3.jpeg)


## Notify on SelectionChanged

SelectionChanged event fires when an item is selected. The parameters of SelectionChanged event are AddedItems and RemovedItems. Added items have the list of recently selected items whereas RemovedItems have the list of recently unselected items.

{% tabs %}

{% highlight XAML %}

<navigation:SfTabControl Margin="50" x:Name="tabControl"
                         SelectionChanged="tabControl_SelectionChanged">
						 
</navigation:SfTabControl>


{% endhighlight %}


{% endtabs %}

{% tabs %}

{% highlight C# %}

private void tabControl_SelectionChanged(object sender, SelectionChangedEventArgs e)

{
	
}

{% endhighlight %}

{% highlight VB %}

Private Sub tabControl_SelectionChanged(ByVal sender As Object, ByVal e As SelectionChangedEventArgs)


End Sub

{% endhighlight %}

{% endtabs %}
