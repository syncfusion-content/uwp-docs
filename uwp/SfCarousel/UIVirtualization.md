---
layout: post
title: UIVirtualization 
description: UIVirtualization
platform: winrt
control: SfCarousel
documentation: ug
---

# UI Virtualization

In UI virtualization concept, only the number of items that can be adaptable to the viewport of our device are arranged. Even, if the numerous items have been added to the collection, it loads only the viewport adaptable count of the carousel Items. Items are added at the right of the view when swiping the countable items in forward direction. At the same time, same number of items are removed at the left of the view for maintaining the same viewport items count. Similarly, items are added at the left of the view when swiping in backward direction for maintaining the same viewport items count. At the time, the same number of items are removed at the right of the view. Using this mechanism, virtualization concept is achieved in the carousel control. 

The following property has been used in UIVirtualization support:

* EnableVirtualization  

## EnableVirtualization

UI Virtualization concept is achieved by enabling the EnableVirtualization property.

N> The default value of the EnableVirtualization property is false.

{% tabs %}

{% highlight xaml %}

	<Page
	x:Class="UIVirtualizationUWP.MainPage"
	xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
	xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
	xmlns:local="using:UIVirtualizationUWP"
	xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
	xmlns:layout="using:Syncfusion.UI.Xaml.Controls.Layout"
	xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
	mc:Ignorable="d">

		<Page.Resources>
			<ResourceDictionary>
				<DataTemplate x:Key="itemTemplate">
					<Image Source="{Binding Image}" 
					Height="100" 
					Width="100"/>
				</DataTemplate>
			</ResourceDictionary>
		</Page.Resources>

		<Page.Content>
			<layout:SfCarousel x:Name="carousel"
			ItemTemplate="{StaticResource itemTemplate}"
			ItemsSource="{Binding ImageCollection}"
			ItemHeight="100"
			ItemWidth="100"
			EnableVirtualization="True"
			VisualMode="LinearMode">
			</layout:SfCarousel>
		</Page.Content>
	</Page>

{% endhighlight %}

{% highlight c# %}

 //Enable load more in SfCarousel

carousel.EnableVirtualization = true;

{% endhighlight %}

{% endtabs %}

![](SfCarousel-images/UIVirtualization.png)

You can find the complete UIVirtualization sample from this [link.](http://www.syncfusion.com/downloads/support/directtrac/general/ze/UIVirtualizationUWP-1730634570.zip )