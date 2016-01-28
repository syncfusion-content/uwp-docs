---
layout: post
title: Overview of Syncfusion SfTileView control for UWP
description: Overview of Syncfusion SfTileView control for UWP
platform: uwp
control: SfTileView
documentation: ug
---

# Dealing with states of TileViewItem

## Setting item state

`State` property is used to set the state of tile view item. The possible values of State are:

* Maximized 
* Normal

At most only one item can be in maximized state and the remaining items are in normal state.

{% tabs %}

{% highlight XAML %}

<layout:SfTileView Width="500" Height="300"
                   x:Name="tileView" MinimizedItemsOrientation="Right">

<layout:SfTileViewItem Background="LightBlue" x:Name="tileItem1"
                       Content="PaulVent" State="Maximized">

<layout:SfTileViewItem.MaximizedContent>

<Border Background="LightBlue">

<TextBlock Text="Description about Paul"/>

</Border>

</layout:SfTileViewItem.MaximizedContent>

</layout:SfTileViewItem>

<layout:SfTileViewItem Background="LightBlue" Content="James">

<layout:SfTileViewItem.MaximizedContent>

<Border Background="LightBlue">

<TextBlock Text="Description about James"/>

</Border>

</layout:SfTileViewItem.MaximizedContent>

</layout:SfTileViewItem>

<layout:SfTileViewItem Background="LightBlue" Content="Carl">

<layout:SfTileViewItem.MaximizedContent>

<Border Background="LightBlue">

<TextBlock Text="Description about Carl"/>

</Border>

</layout:SfTileViewItem.MaximizedContent>

</layout:SfTileViewItem>

<layout:SfTileViewItem Background="LightBlue" Content="Niko">

<layout:SfTileViewItem.MaximizedContent>

<Border Background="LightBlue">

<TextBlock Text="Description about Niko"/>

</Border>

</layout:SfTileViewItem.MaximizedContent>

</layout:SfTileViewItem>

</layout:SfTileView>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

tileItem1.State = Syncfusion.UI.Xaml.Controls.Layout.TileViewItemState.Maximized;

{% endhighlight %}

{% endtabs %}

![](Dealing-with-item-state-images/Dealing-with-item-state-img1.jpeg)

## Maximizing item programmatically

`MaximizedItem` property is used to get the instance of maximized tile view item. It is a read-only property.

{% tabs %}

{% highlight C# %}

SfTileViewItem maximizedItem = tileView.MaximizedItem;

{% endhighlight %}

{% endtabs %}

## Retrieving the Minimized items

`MinimizedItems` property is used to get a collection of minimized tile view items. It is a read-only property.

{% tabs %}

{% highlight C# %}

ObservableCollection<object> minimizedItems = tileView.MinimizedItems;

{% endhighlight %}

{% endtabs %}

