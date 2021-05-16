---
layout: post
title: Selecting Items in UWP Tree Navigator control | Syncfusion
description: Learn here all about Selecting Items support in Syncfusion UWP Tree Navigator (SfTreeNavigator) control and more.
platform: uwp
control: SfTreeNavigator
documentation: ug
---

# Selecting Items in UWP Tree Navigator (SfTreeNavigator)

TreeNavigator items can be selected in one or more ways as give below:

## Selecting item using SelectedItem

`SelectedItem` property is used to select an item using its instance and it can be set as follows:

{% tabs %}

{% highlight XAML %}

<navigation:SfTreeNavigator x:Name="treeNavigator" SelectedItem="wpf">

<navigation:SfTreeNavigatorItem Header="WPF" x:Name="wpf"/>

<navigation:SfTreeNavigatorItem Header="Silverlight"/>

<navigation:SfTreeNavigatorItem Header="Windows Phone"/>

<navigation:SfTreeNavigatorItem Header="WinRT"/>

<navigation:SfTreeNavigatorItem Header="Universal"/>

</navigation:SfTreeNavigator>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

treeNavigator.SelectedItem = WPF;

{% endhighlight %}

{% highlight VB %}

treeNavigator.SelectedItem = WPF

{% endhighlight %}

{% endtabs %}

![Selecting item using SelectedItem](Selecting-tree-items-images/Selecting-tree-items-img1.jpeg)

## Selecting item by change IsSelected

`IsSelected` property is used to check whether an item is selected or not. An item can also be selected as follows:

{% tabs %}

{% highlight XAML %}

<navigation:SfTreeNavigator>

<navigation:SfTreeNavigatorItem Header="WPF" IsSelected="True" x:Name="wpf"/>

<navigation:SfTreeNavigatorItem Header="Silverlight"/>

<navigation:SfTreeNavigatorItem Header="Windows Phone"/>

<navigation:SfTreeNavigatorItem Header="WinRT"/>

<navigation:SfTreeNavigatorItem Header="Universal"/>

</navigation:SfTreeNavigator>

{% endhighlight %}

{% endtabs %}


{% tabs %}


{% highlight C# %}

wpf.IsSelected = true;

{% endhighlight %}

{% highlight VB %}

wpf.IsSelected = True

{% endhighlight %}

{% endtabs %}

![IsSelected property](Selecting-tree-items-images/Selecting-tree-items-img2.jpeg)

## Select Item though code-behind

Select method is used to select an item with its instance and it can be used as follows:

{% tabs %}

{% highlight XAML %}

<navigation:SfTreeNavigator x:Name="treeNavigator">

<navigation:SfTreeNavigatorItem Header="WPF" x:Name="wpf"/>

<navigation:SfTreeNavigatorItem Header="Silverlight"/>

<navigation:SfTreeNavigatorItem Header="Windows Phone"/>

<navigation:SfTreeNavigatorItem Header="WinRT"/>

<navigation:SfTreeNavigatorItem Header="Universal"/>

</navigation:SfTreeNavigator>

{% endhighlight %}

{% endtabs %}

{% tabs %}


{% highlight C# %}

treeNavigator.Select(wpf);

{% endhighlight %}

{% highlight VB %}

treeNavigator.Select(wpf)

{% endhighlight %}

{% endtabs %}

![Select Item though code-behind](Selecting-tree-items-images/Selecting-tree-items-img3.jpeg)

## Retrieving the selected hierarchical level

DrillDownItem is used to get the instance of an item that holds the items in current hierarchical level. It is a read only property containing `SfTreeNavigator` itself as DrillDownItem when no item is selected.

{% tabs %}

{% highlight XAML %}

<navigation:SfTreeNavigator x:Name="treeNavigator">

<navigation:SfTreeNavigatorItem Header="WPF"/>

<navigation:SfTreeNavigatorItem Header="Silverlight"/>

<navigation:SfTreeNavigatorItem Header="Windows Phone"/>

<navigation:SfTreeNavigatorItem Header="WinRT"/>

<navigation:SfTreeNavigatorItem Header="Universal"/>

</navigation:SfTreeNavigator>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

private void treeNavigator_Loaded(object sender, RoutedEventArgs e)

{

HeaderedItemsControl item = treeNavigator.DrillDownItem;

}

{% endhighlight %}

{% highlight VB %}

Private Sub treeNavigator_Loaded(ByVal sender As Object, ByVal e As RoutedEventArgs)


Dim item As HeaderedItemsControl = treeNavigator.DrillDownItem

End Sub

{% endhighlight %}

{% endtabs %}

## Notifying selection changed

SelectionChanged event is used to notify whenever a selection change takes place. The event is hooked as follows:

{% tabs %}

{% highlight XAML %}

<navigation:SfTreeNavigator x:Name="treeNavigator" SelectionChanged="treeNavigator_SelectionChanged">

<navigation:SfTreeNavigatorItem Header="WPF"/>

<navigation:SfTreeNavigatorItem Header="Silverlight"/>

<navigation:SfTreeNavigatorItem Header="Windows Phone"/>

<navigation:SfTreeNavigatorItem Header="WinRT"/>

<navigation:SfTreeNavigatorItem Header="Universal"/>

</navigation:SfTreeNavigator>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

private void treeNavigator_SelectionChanged(object sender, SelectionChangedEventArgs e)

{

}

{% endhighlight %}

{% highlight VB %}

Private Sub treeNavigator_SelectionChanged(ByVal sender As Object, ByVal e As SelectionChangedEventArgs)


End Sub

{% endhighlight %}

{% endtabs %}

## Notifying click on item

ItemClicked event is used to notify whenever an item is clicked. It is fired for both mouse left button and right button click. The event arguments are 

ItemPosition – The (x,y) point where SfTreeNavigator item is clicked

MouseMode – Determines whether left or right mouse button click

The event is hooked as follows:

{% tabs %}

{% highlight XAML %}

<navigation:SfTreeNavigator x:Name="treeNavigator">

<navigation:SfTreeNavigatorItem Header="WPF" ItemClicked="SfTreeNavigatorItem_ItemClicked"/>

<navigation:SfTreeNavigatorItem Header="Silverlight"/>

<navigation:SfTreeNavigatorItem Header="Windows Phone"/>

<navigation:SfTreeNavigatorItem Header="WinRT"/>

<navigation:SfTreeNavigatorItem Header="Universal"/>

</navigation:SfTreeNavigator>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

private void SfTreeNavigatorItem_ItemClicked(object Sender, Syncfusion.UI.Xaml.Controls.Navigation.ItemClickEventArgs args)

{

}

{% endhighlight %}

{% highlight VB %}

Private Sub SfTreeNavigatorItem_ItemClicked(ByVal Sender As Object, ByVal args As Syncfusion.UI.Xaml.Controls.Navigation.ItemClickEventArgs)


End Sub

{% endhighlight %}

{% endtabs %}

## Navigate thorough code-behind

SfTreeNavigator.GoBack() method is used to navigate a hierarchical level back in the tree if applicable. 

{% tabs %}

{% highlight C# %}

treeNavigator.GoBack();

{% endhighlight %}

{% highlight VB %}

treeNavigator.GoBack()

{% endhighlight %}

{% endtabs %}

